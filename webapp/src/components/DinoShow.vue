<template>
    <div id="card">

        <strong>{{ name }}</strong> | {{ diet }}

    </div>
</template>

<script>



export default {
    name: 'DinoCounter',
    props: ["name", "diet"],
    data () {
        return {

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

</style>
