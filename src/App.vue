<template>
    <div class="container">
        <app-header v-bind:quoteCount="quotesArray.length" v-bind:maxQuotes="maxQuotes"> </app-header>
        <!--here, we are lsitening to the event emittted in the child-->
        <!-- to access the data that is passed from the child comonent, but don't need to write newQuote(quote)-->
        <!-- <app-new-quote v-on:quoteAdded="newQuote($event)"></app-new-quote> -->
        <app-new-quote v-on:quoteAdded="newQuote"></app-new-quote>
        <app-quote-grid v-bind:quotes="quotesArray"
                        v-on:quoteDeleted="deletingOurQuote($event)"> </app-quote-grid>  <!-- listenng to our own event -->
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">
                    Info: Click on a Quote to delete it!
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    import Header from './components/Header.vue';


    export default {
        data:function(){
            return{
                quotesArray:[
                    'Just a quote to see something'
                ],
                maxQuotes: 10
            }
        },
        methods: {
            newQuote(quote){
                if(this.quotesArray.length >= this.maxQuotes){
                    return alert('Plese delete quotes first');
                }
                this.quotesArray.push(quote);
            },
            deletingOurQuote(index){
                this.quotesArray.splice(index,1); //modify the existing array andremove 1 elem at position index.
            }
        },
        components: {
            'app-quote-grid': QuoteGrid,
            'app-new-quote': NewQuote,
            appHeader: Header
        }
    }
</script>

<style>
</style>