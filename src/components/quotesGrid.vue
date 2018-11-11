<template>
    <div class="row">
       <app-quote v-for="(quote, index) in quotes" :key="index" @click.native="deleteHandler">
            {{ quote }}
       </app-quote>
    </div>
</template>

<script>
    import Quote from './quote.vue';
    export default {
        props: {
            quotes: {
                type: Array
            }
        },
        components: {
            appQuote: Quote
        },
        methods: {
            deleteHandler(evt) {
                this.$emit('deleteQuoteHandler', evt.target.innerText);
            }
        }
    }
</script>

<style>
   
</style>
