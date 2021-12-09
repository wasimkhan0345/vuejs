<template>
  <div class="container">
    <app-header :maxQuote="maxQuotes" :quoteCount="quotes.length"></app-header>
    <app-new-quote @quoteAdded="newquote" ></app-new-quote>
    <app-qoute-grid :quotes="quotes" @QuoteDelete="quoteDeleted"></app-qoute-grid>
    <div class="row">
      <div class="col-lg-12 text-center">
        <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
      </div>
    </div>
  </div>
</template>

<script>

import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
import HeaderQuote from './components/Header.vue'



export default {
  data: function() {
    return {
      quotes: ['Just a quote to see something'],
      maxQuotes: 10
    }
  },
  components: {
    appQouteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appHeader: HeaderQuote
  },
  methods: {
    newquote(quote) {
      if(this.quotes.length >= this.maxQuotes) {
        return alert("Please delete quote first!");
      }
      this.quotes.push(quote);
    },
    quoteDeleted(index) {
      console.log(index);
      this.quotes.splice(index,1);
    }
  }
}
</script>

<style>
</style>
