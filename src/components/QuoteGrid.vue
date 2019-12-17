<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quoteProp" :key="index" v-on:click.native="deleteQuote(index)">{{ quote }}</app-quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue'

    export default {
        props: ['quoteProp'],
        components: {
            appQuote: Quote
        },
        methods: {
            deleteQuote: function(index) {
                this.$emit('quoteDeleted', index)
            }
        }
    }
</script>

<style>
</style>