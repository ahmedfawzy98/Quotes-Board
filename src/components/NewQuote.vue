<template>
    <div class="container">
        <div class="form-group">
            <label class="font-weight-bold">Quote</label>
            <textarea 
            class="form-control" 
            rows="3"
            v-model="quoteText"
            ></textarea>
        </div>
        <div class="text-center">
            <button 
                class="btn btn-primary mb-3"
                @click="addQuote">
                Add Quote
            </button>
        </div>
    </div>
</template>

<script>
    import { eventBus } from '../main'
    export default {
        data: function(){
            return {
                quoteText: ''
            };
        },
        props: ['quotes'],
        methods: {
            addQuote(){
                if(this.quotes.length < 10){
                    this.quotes.push(this.quoteText);
                    eventBus.$emit('newQuoteAdded', this.quotes.length);
                    eventBus.$emit('newQuotes', this.quotes);
                    this.quoteText = '';
                }else{
                    alert('Too many Quotes! Delete some before adding new ones!');
                }
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>