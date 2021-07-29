<template>
  <div id="app" class="container">
  <appHeader :quoteCount="quotes.length" :maxQuotes = "maxQuotes"></appHeader>
    <newQuote @quoteAdded="newQuote"> </newQuote>
    <appQuoteGrid :quotes="quotes" @quoteDeleted= "deleteQuote"></appQuoteGrid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-danger">
          <h1>Info: Click here to delete the quote</h1>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import Header from './components/Header'
import QuotesGrid from './components/QuotesGrid'
import NewQuote from './components/NewQuote'
export default {
  name: 'App',
  components: {
    appQuoteGrid: QuotesGrid,
    newQuote: NewQuote,
    appHeader: Header
  
  },
  data() {
    return {
      quotes: [
        'Just a quote'
      ],
      maxQuotes: 10
    }
  },
  methods:{
    newQuote(quote){//use for the emmit method from our "NewQuote" component..intializing the function we passed to the "quoteAdded" string in our App.vue
        if(this.quotes.length >= this.maxQuotes){
          return alert('Please delete quote first!');
        }
        
        this.quotes.push(quote);
    },
    deleteQuote(index){
      this.quotes.splice(index,1);
    },
   
  }
}
</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
