<template>
    <div class="container">
        <app-quote-grid :quoteProp="quotes"></app-quote-grid>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';

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
        components: {
            appQuoteGrid: QuoteGrid
        }
    }
</script>

<style>
</style>
