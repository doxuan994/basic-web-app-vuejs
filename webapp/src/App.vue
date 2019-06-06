<template>
    <div id="app">
        <!-- <HelloWorld/> -->
        <!-- <Class/> -->
        <HandleDOMEvents/>
    </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Class from './components/Class'
import ConditionalRendering from './components/ConditionalRendering'
import HandleDOMEvents from './components/HandleDOMEvents'

export default {
    name: 'App',
    components: {
        HelloWorld,
        Class,
        ConditionalRendering,
        HandleDOMEvents
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
