<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header><!--passing these to header comp -->
     <app-new-quote @quoteAdded="newQuote"></app-new-quote> <!-- Listening to event emitted -->
     <!--passing to quote grid -->
    <app-quote-grid  :quotes="quotes" @quoteDeleted="deleteQuote"> <!--@quoteDeleted="deleteQuote" listening to event emitted, deleteQuote is method below  -->
        </app-quote-grid> 
    <div class="row">
        <div class="col-sm-12 text-center">
            <div class="alert alert-info">Info: Click on a quote to delete it </div>           
            </div>
    </div>
    </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue'
import NewQuote from './components/NewQuote.vue'
import Header from './components/Header.vue'
    export default {
        data: function(){
            return {
                quotes: [ // passing this array of quotes to quote-grid comp
                    'Just a sample'
                ],
                maxQuotes: 10
            }
        },
        methods: {
           newQuote( quote){ //accessing (listening) data passed by event (new quote comp emits new quote created)
              if(this.quotes.length >= this.maxQuotes){
                  return alert('Please delete the quotes first')
              }
              this.quotes.push(quote)
           },
           deleteQuote(index){
               this.quotes.splice(index, 1)
           }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            appHeader: Header
        }
    }
</script>

<style>
</style>
