<template>
    <div id="app">
        <!-- <HelloWorld/> -->
        <!-- <Class/> -->
        <!-- <BindValueToInputFields/> -->
        <!-- <DinoCounter v-for="dino in dinos"
            :name="dino.name"
            :initialQuantity="dino.quantity"
            :key="dino.id"
            @increment="incrementTotal">
        </DinoCounter> -->

        <!-- <DinoShow v-for="dino in dinos"
            :name="dino.name"
            :diet="dino.diet"
            :key="dino.id">
        </DinoShow> -->

        <span @click="toggle">{{ toggleLabel }}</span>



            <component :is="currentView" v-for="dino in dinos"
                :name="dino.name"
                :initialQuantity="dino.quantity"
                :diet="dino.diet"
                :key="dino.id"
                @increment="incrementTotal">
            </component>







        <p>Total Dinosaurs: {{ total }}</p>
    </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Class from './components/Class'
import ConditionalRendering from './components/ConditionalRendering'
import HandleDOMEvents from './components/HandleDOMEvents'
import BindValueToInputFields from './components/BindValueToInputFields'
import DinoCounter from './components/DinoCounter'
import DinoShow from './components/DinoShow'

export default {
    name: 'App',
    components: {
        HelloWorld,
        Class,
        ConditionalRendering,
        HandleDOMEvents,
        BindValueToInputFields,
        DinoCounter,
        DinoShow
    },
    data() {
        return {
            dinos: [
                { name: "Tyrannosaurus", quantity: 5, diet: 'Carnivore' },
                { name: "Triceratops", quantity: 4, diet: 'Herbivore' },
                { name: "Stegosaurus", quantity: 1, diet: 'Herbivore' }
            ],
            total: 0,
            currentView: 'DinoCounter'
        }
    },
    methods: {
        incrementTotal(amount) {
            this.total += amount;
        },
        toggle() {
            this.currentView = this.currentView == 'DinoCounter' ? 'DinoShow' : 'DinoCounter';
        }
    },
    computed: {
        toggleLabel() {
            return this.currentView == 'DinoCounter' ? 'Edit' : 'Show';
        }
    }
}
</script>

<style>
#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
