<template>
    <div class="row">
        <!--To delete a simgle quote, use @click.native, .native is a modifier, tells vue.js that react to this component
        if it happens to the native element -->
        <app-quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)"> {{ quote }}</app-quote>
    </div>
</template>

<script>
import Quote from './Quote.vue';

export default {
    props : ['quotes'], //get array of quotes from outside
    components: {
        'app-quote': Quote
    },
    methods: {
        deleteQuote(index){  //to delete a quote, we need the index of that quote.
            this.$emit('quoteDeleted',index); //here emiting the event.
        }
    }
}
</script>

<style scoped>

</style>