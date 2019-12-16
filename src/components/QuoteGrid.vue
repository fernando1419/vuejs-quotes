<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quoteProp" :key="index">{{ quote }}</app-quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue'

    export default {
        props: ['quoteProp'],
        components: {
            appQuote: Quote
        },
    }
</script>

<style>
</style>