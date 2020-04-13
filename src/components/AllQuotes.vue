<template>
    <div class="container">
        <div class="row">
            <div class="col-4 mb-3" v-for="(quote, i) in quotes" :key="quote">
                <quote :quotes="quotes" :index="i">
                    <p>{{ quote }}</p>
                </quote>
            </div>
        </div>
    </div>
</template>

<script>
    import { eventBus } from '../main'
    import Quote from './Quote'
    export default {
        props: ['quotes'],
        created(){
            eventBus.$on('newQuotes', (newQuotes) => {
                this.quotes = newQuotes;
            });
            eventBus.$on('quoteDeleted', (newQuotes) => {
                this.quotes = newQuotes;
            })
        },
        components: {
            Quote
        }
        
    }
</script>

<style lang="scss" scoped>

</style>
