<template>
    <div class="container">
        <app-progress-bar :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-progress-bar>
        <app-new-quote v-on:quoteCreated="addQuote"></app-new-quote>
        <app-quote-grid v-bind:quoteProp="quotes" v-on:quoteDeleted="eraseQuote"></app-quote-grid>
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
    import ProgressBar from './components/ProgressBar.vue';

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
                if (quote.length == 0) {
                    return alert('Please some text for a quote!');
                }
                
                if (this.quotes.length >= this.maxQuotes) {
                    return alert('Please delete a quote first!');
                }

                this.quotes.push(quote);
            },
            eraseQuote: function(index) {
                // console.log('erasing quote...', index);
                this.quotes.splice(index, 1);
            }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            appProgressBar: ProgressBar
        }
    }
</script>

<style>
</style>
