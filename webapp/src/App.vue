<template>
    <div id="app">
        <!-- <HelloWorld/> -->
        <!-- <Class/> -->
        <!-- <BindValueToInputFields/> -->
        <DinoCounter v-for="dino in dinos"
            :name="dino.name"
            :initialQuantity="dino.quantity"
            :key="dino.id"
            @increment="incrementTotal">

        </DinoCounter>

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

export default {
    name: 'App',
    components: {
        HelloWorld,
        Class,
        ConditionalRendering,
        HandleDOMEvents,
        BindValueToInputFields,
        DinoCounter
    },
    data() {
        return {
            dinos: [
                { name: "Tyrannosaurus", quantity: 5 },
                { name: "Triceratops", quantity: 4 },
                { name: "Stegosaurus", quantity: 1 }
            ],
            total: 0
        }
    },
    methods: {
        incrementTotal(amount) {
            this.total += amount;
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
