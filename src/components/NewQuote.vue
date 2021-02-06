<template>
    <div class="row">
        <form>
        <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md offset-3 form-group">
            <label>Quote</label>
            <textarea class="form-control" rows="3" v-model="quote"></textarea> <!-- v-model is 2 way binding -->
        </div>

        <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md offset-3 form-group">
            <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
        </div>
        </form>
    </div>
</template>

<script>
export default {
    data: function(){
        return{
            quote: ''  //quote must be same as v-model="quote", quote has value that what we put in above textarea.
        }
    },
    methods: {
        createNew(){  //send the quote created here to the parent component.
            this.$emit('quoteAdded', this.quote);  //emit the quoteAdded event
            this.quote = '';  //reset quote afer sending it.
        }   
    }
}
</script>

<style scoped>

</style>