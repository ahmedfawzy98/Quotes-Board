<template>
    <div class="m-2">
    <label class="mt-5 font-weight-bold" style="font-size:25px;">Quotes Added</label>
    <div class="progress mb-5" style= "height: 25px;">
        <div class="progress-bar" :style="barStyle">{{ quotesNumber }} / 10</div>
    </div>
    </div>
</template>

<script>
    import { eventBus } from '../main' 
    export default {
        props: ['quotesNumber'],
        computed: {
            barStyle(){
                return {
                    width: (this.quotesNumber / 10) * 100 + '%'
                };
            }
        },
        created(){
            eventBus.$on('newQuoteAdded', (length) => {
                this.quotesNumber = length;
            });
        }
    }
</script>

<style lang="scss" scoped>

</style>