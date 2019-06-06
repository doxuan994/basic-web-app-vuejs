<template>
    <div id="card">
        <header>
            {{ title }}
        </header>

        <div>
            <input type="text" id="itemForm" @keypress.enter="addItem" v-model="item.text">
            <!-- <input type="text" id="itemForm" @keypress.enter="addItem" v-model="input"> -->
            <button @click="addItem">{{ buttonText }}</button>
        </div>


        <div v-html="content"></div>


        <div class="content">

            <ul>
                <h3>List 1</h3>
                <li v-for="(item, index) in items">

                    <button @click="adddOneToSpecie(index)">+</button>

                    {{ item.quantity }}

                    <button @click="removeOneFromSpecie(index)">-</button>



                    {{ item.text }}

                    <button @click="deleteItem(index)">Make Extinct</button>
                </li>
            </ul>

            <ul>
                <h3>List 2</h3>
                <li v-for="dino in dinos">
                    <h4>{{ dino.text | capitalize }}</h4>
                    <span>The {{ dino.text | undercase }} weights {{ dino.weight }}.</span>
                    <br>
                    <a href="">{{ dino.text | undercase | url }}</a>
                </li>
            </ul>

            <ul>
                <li>Total Dinosaurs: {{ totalDinosComputed }} <span>Updated: {{ dinosUpdated }}</span> </li>
                <li>Total Species: {{ totalSpeciesComputed }} <span>Updated: {{ speciesUpdated }}</span> </li>
            </ul>

        </div>




    </div>
</template>

<script>
import _ from 'lodash';


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
                { text: "Velociraptor", quantity: 5 },
                { text: "Tricerators", quantity: 3 },
                { text: "Stegosaurus", quantity: 6 }
            ],
            dinos: [
                {
                    text: 'Velociraptor',
                    weight: '15 kg',
                },
                {
                    text: 'tricerators',
                    weight: '6,000 kg'
                },
                {
                    text: 'Stegosaurus',
                    weight: "2,500 kg"
                }
            ],
            totalDinos: 0,
            totalSpecies: 0,
            dinosUpdated: 0,
            speciesUpdated: 0,
            buttonText: "Add Dinosaur",
            input: ""
        }
    },
    methods: {
        addItem() {
            this.items.push(this.item);
        },
        deleteItem(index) {
            this.items.splice(index, 1);
        },
        adddOneToSpecie(index) {
            this.items[index].quantity++;
        },
        removeOneFromSpecie(index) {
            this.items[index].quantity--;
        }
    },
    filters: {
        capitalize(value) {
            if (!value) return;
            value = value.toString();
            return value.charAt(0).toUpperCase() + value.slice(1);
        },
        undercase(value) {
            if (!value) return;
            value = value.toString();
            return value.charAt(0).toLowerCase() + value.slice(1);
        },
        url(value) {
            if (!value) return;
            value = value.toString();

            return "https://www.wikipedia.org/wiki/" + value;
        }
    },
    computed: {
        totalDinosComputed() {
            this.dinosUpdated += 1;
            let sum = 0;
            let items = this.items;

            for (let i = 0; i < items.length; i++) {
                sum += items[i].quantity;
            }

            return sum;
        },
        totalSpeciesComputed() {
            this.speciesUpdated += 1;
            return this.items.length;
        }
    },
    watch: {
        input: _.debounce(function() {
            this.buttonText = this.input !== "" ? "Add " + this.input : "Add Dinosaur";
        }, 250)
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
    border: 3px solid gold;
    border-radius: 25px;


}
.content {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
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


    padding: 0;
    margin: 1em;

    margin-top: 2em;

    border: 3px solid gold;

    flex-basis: 460px;
}
li {
    list-style: none;

    border: 2px solid #ccc;

    margin: 0.5em;

    padding: 0.5em 0;

}
</style>
