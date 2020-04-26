<template>
    <div class="row">
        <p> quote grid </p>
        <!--sending each quote created using slot to quote comp -->
        <!--we are getting quotes from parent app.vue and passing only each quote template to quote comp
        as the quotes are present here and we are just passing the template to display quotes in quote comp 
        to delete quote when clicked should be performed in this comp as quotes are here but action should take
        place in quote comp. i.e when we click quote that quote temp should be deleted from quote comp hece we use .native-->
        <app-quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)">{{ quote }}</app-quote> 

        </div>
</template>

<script>
import Quote from './Quote.vue'

export default {
    props:['quotes'], // getting quotes from parent comp (app.vue)
    components: {
        appQuote: Quote
    },
    methods: {
        deleteQuote(index){
            this.$emit('quoteDeleted', index) // emitting data (index) which will be listened by parent comp app.vue
        // we emit event here to delete quote because the array of quotes are in app.vue
        }
    }
}
</script>
 
     
     <style>
     
     </style>
 