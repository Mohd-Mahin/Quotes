<template>
    <div class="row">
        <form>
            <div class="col-sm-10 col-sm-offset-1 col-md-6 col-xs-12 col-md-offset-3 form-group">
                <label for="quoteTextArea">Quote</label>
                <textarea name="quoteTextArea" id="quoteTextArea" rows="3" class="form-control" v-model="quote"></textarea>
            </div>
            <div class="col-sm-8 col-md-6 col-xs-12 col-sm-offset-2 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
            </div>
        </form>
    </div>
</template>
<script>
    export default {
        data: function() {
            return {
                quote: ''
            }
        },
        methods: {
            createNew() {
                if (!this.quote) return;
                this.$emit('addNewQuote', this.quote);
                this.quote = '';
            }
        }
    }
    
</script>

<style>

</style>
