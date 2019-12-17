<template>
    <div class="container">
        <app-new-quote v-on:quoteCreated="addQuote"></app-new-quote>
        <app-quote-grid v-bind:quoteProp="quotes"></app-quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on a quote to Delete it!</div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';

    export default {
        data: function() {
            return {
                quotes: [
                    'One testing element',
                    'Second Element',
                    'Third element!',
                    'Fourth element!'
                ],
                maxQuotes: 10
            }
        },
        methods: {
            addQuote: function(quote) {
                if (quote.length > 0) 
                {
                    this.quotes.push(quote)
                }
            }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote
        }
    }
</script>

<style>
</style>
