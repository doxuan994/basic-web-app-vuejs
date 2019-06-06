<template>
    <div id="box">
        <div>
            <input type="checkbox" id="checkbox" v-model="checked">
            <label for="checkbox">This box is {{ checked ? 'checked' : 'unchecked' }}</label>
        </div>


        <div v-for="dino in dinos">
            <input type="radio" :value="dino" v-model="chosenDino">
            <label>{{ dino }}</label>
        </div>

        <span>Favorite: {{ chosenDino }}</span>
        




        <hr>

        <select v-model="selectedPeriods" multiple>
            <option v-for="period in periods" :value="period.value">{{ period.name }}</option>
        </select>
        <br>
        <span>Selected Period Value: {{ selectedPeriods }}</span>
        <hr>
        <input type="text" v-model="single">
        <p>{{ single }}</p>

        <textarea v-model="message" placeholder="add multiple lines"></textarea>
        <p style="white-space: pre;">{{ message }}</p>
    </div>
</template>

<script>
export default {
    name: 'BindValueToInputFields',
    data () {
        return {
            checked: false,
            chosenDino: '',
            dinos: [
                "Triceratops", "Velociraptor", "Tyrannosaurus"
            ],
            selectedPeriods: [],
            periods: [
                { name: 'Triassic', value: 1 },
                { name: 'Jurassic', value: 2 },
                { name: 'Cretaceous', value: 3 },
            ],
            single: '',
            message: ''
        }
    },
    methods: {

    },
    filters: {

    },
    computed: {

    },
    watch: {

    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#box {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
}

</style>
