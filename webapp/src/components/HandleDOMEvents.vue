<template>
    <div id="card">
        <header>Dinosaurs</header>
        <!-- <button @click="total += 1">Add Dinosaur</button> -->
        <!-- <button @click="addDinos">Add {{ amount }} Dinosaur</button>
        <input type="number" v-model="amount" @keyup.enter="addDinos"> -->


        <form @submit.prevent="addDinos">
            <button>Add {{ amount }} Dinosaur</button>
            <input type="number" v-model="amount">
        </form>

        <p>You have {{ total }} dinosaurs!</p>
    </div>
</template>

<script>



export default {
    name: 'HandleDOMEvents',
    data () {
        return {
            total: 0,
            amount: null
        }
    },
    methods: {
        addDinos: function() {

            this.total += Number(this.amount);
        }
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


</style>
