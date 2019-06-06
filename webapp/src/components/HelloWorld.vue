<template>
    <div id="card">
        <header>
            {{ title }}
        </header>

        <div>
            <input type="text" id="itemForm" @keypress.enter="addItem" v-model="item.text">
            <button @click="addItem">Add Dinosaur</button>
        </div>



        <div v-html="content"></div>

        <ul>
            <li v-for="item in items">{{ item.text }}</li>
        </ul>


    </div>
</template>

<script>
export default {
    name: 'HelloWorld',
    data () {
        return {
            title: 'Dinosaurs',
            content: "<strong>Dinosaurs</strong> are a diverse group of animals of the clade <em>Dinosaurs</em> that first appeared during the Triassic period.",
            item: {
                text: ''
            },
            items: [
                { text: "Velociraptor" },
                { text: "Tricerators" },
                { text: "Stegosaurus" }
            ],

        }
    },
    methods: {
        addItem() {
            this.items.push(this.item);
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
    box-sizing: border-box;
}
body {
    padding: 0;
    margin: 0;
}
button, input {
    background-color: #fff;
    padding-top: 0.5em;
    padding-bottom: 0.5em;
    border: 2px solid #ccc;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    font-size: 1em;
}
#card {
    max-width: 460px;
    border: 3px solid #777;
    border-radius: 25px;
}
div {
    margin: 1em;
}
header {
    padding: 1em;
    background-color: gold;
    border-top-left-radius: 22px;
    border-top-right-radius: 22px;

    color: #fff;
    font-size: 1.5em;
}
ul {
    display: flex;
    flex-direction: column;
    justify-content: center;

    padding: 0;
    margin: 1em;
}
li {
    list-style: none;

    border: 2px solid #ccc;

    margin-top: 0.5em;
    margin-bottom: 0.5em;

    padding: 0.5em 0;

}
</style>
