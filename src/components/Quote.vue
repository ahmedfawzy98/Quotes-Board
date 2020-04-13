<template>
    <div>
        <div class="card">
            <div class="card-body btn" @click="remove">
                <slot></slot>
            </div>
        </div>
    </div>
</template>

<script>
    import { eventBus } from '../main'
    export default {
        props: ['quotes', 'index'],
        methods:{
            remove(){
                this.quotes.splice(this.index, 1);
                eventBus.$emit('quoteDeleted', this.quotes);
            }
        },
    }
</script>

<style scoped>
    .btn:hover{
        background-color: rgb(255, 224, 224);
    }

</style>
