<template>
    <div class="row">
        <div class="col-sm-12">
            <h3>Quotes Added</h3>
            <div class="progress">
                <div class="progress">
                    <div class="progress-bar" role="progressbar" aria-valuenow="60" aria-valuein="0" aria-valuemax="100"
                        v-bind:style="{width: (quoteCount / maxQuotes) * 100 + '%'}">   
                        <!-- 5/10*100 -> .5*100 ->50 -> 50% -->
                        <!--adjust the width of the inner div to control how far the progress bar has moved-->
                        {{ quoteCount }} \ {{ maxQuotes }}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['quoteCount','maxQuotes']
}
</script>

<style>

</style>