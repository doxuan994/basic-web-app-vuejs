<template>
    <div id="card">

        <button @click="increment">{{ quantity }}</button>

        {{name}}

    </div>
</template>

<script>



export default {
    name: 'DinoCounter',
    props: ["name", "initialQuantity"],
    data () {
        this.$emit('increment', this.initialQuantity);
        return {
            quantity: this.initialQuantity
        }
    },
    methods: {
        increment() {
            this.quantity += 1;
            this.$emit('increment', 1);
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
