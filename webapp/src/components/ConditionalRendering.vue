<template>
    <div id="card">
        <header>{{ title }}</header>

        <button
            :class="[sizeToggle ? 'large' : '', { 'rounded': isRounded }]"
            :style="styles"
            :disabled="disabled">
            Start Tour
        </button>

        <hr>

        <div class="flex-container">
            <h4>Options</h4>

            <ul class="flex-container">
                <li>
                    <input type="checkbox" v-model="sizeToggle">
                    <label>Large</label>
                </li>
                <li>
                    <input type="checkbox" id="round" v-model="isRounded">
                    <label for="round">Round</label>
                </li>
                <li>
                    <input type="checkbox" v-model="disabled">
                    <label>Disabled</label>
                </li>
                <li>
                    <input type="text" v-model="backgroundColor">
                    <label>Background Color</label>
                </li>
                <li>
                    <input type="text" v-model="fontColor">
                    <label>Font Color</label>
                </li>
                <li>
                    <input type="range" v-model="range" min="15" max="85">
                    <label>Position</label>
                </li>
            </ul>
        </div>


    </div>
</template>

<script>



export default {
    name: 'ConditionalRendering',
    data () {
        return {
            title: 'Style Binding',
            isRounded: false,
            sizeToggle: false,
            disabled: false,
            backgroundColor: '#ccc',
            fontColor: '#000',
            range: 50
        }
    },
    methods: {

    },
    filters: {

    },
    computed: {
        styles() {
            return {
                color: this.fontColor,
                background: this.backgroundColor,
                'margin-left': this.range + "%"
            }
        }
    },
    watch: {

    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
li {
    list-style: none;
}
#card {
    max-width: 600px;
    border: 3px solid black;
}

header {
    padding: 1em;
    background-color: #21ce99;
    color: #fff;
}
button {
    background-color: #21ce99;
    padding: 10px;
    border: 0;
    margin: 1em;
    color: #fff;
    font-size: 1em;
}

.large {
    font-size: 2em;
}

.rounded {
    border-radius: 2em;
}

.disabled {

}

h4 {
    padding-left: 40px;
}
li {
    margin: 0.5em;

}

input {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    color: #2c3e50;
    font-size: 1.2em;
}

.flex-container {
    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
    align-items: flex-start;
}

</style>
