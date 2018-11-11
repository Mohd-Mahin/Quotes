<template>
    <div class="container">
        <header-progress-bar :range="quotes.length"></header-progress-bar>
        <app-add-quote @addNewQuote="addQuote"></app-add-quote>
        <app-quote-grid :quotes="quotes" @deleteQuoteHandler="delQuote"></app-quote-grid>
        <div class="row">
            <div class="col-sm-12">
                <div class="alert alert-danger">
                    Info: Click on a Quote to delete it!.
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import quoteGrid from './components/quotesGrid.vue';
    import addQuote from './components/addQuote.vue';
    import headerProgressBar from './components/header.vue';

    export default {
        data: function() {
            return {
                maxQuotes: 10,
                quotes: [
                    'Just a quote to see something!!',
                ]
            }
        },
        methods: {
            addQuote(quoteText) {
                if (this.maxQuotes == this.quotes.length) {
                    alert('Maximum 10 quotes can be added!!!');
                    return;
                }
                this.quotes.push(quoteText);
            },
            delQuote(val) {
                let index = this.quotes.indexOf(val);
                // console.log(index)
                if (index == -1) return;
                this.quotes.splice(index, 1);
            }
        },
        components: {
            appQuoteGrid: quoteGrid,
            appAddQuote: addQuote,
            headerProgressBar
        }
    }
</script>

<style>
</style>
