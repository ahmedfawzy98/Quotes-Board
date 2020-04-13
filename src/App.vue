<template>
  <div>
    <progressBar :quotesNumber="quotes.length"></progressBar>
    <newQuote :quotes="quotes"></newQuote>
    <allQuotes :quotes="quotes"></allQuotes>
    <div class="alert alert-primary mt-4 text-center ml-5 mr-5">
      Info: Click on a Quote to delete it
    </div>
  </div>
</template>

<script>
  import Header from './components/Header'
  import NewQuote from './components/NewQuote'
  import AllQuotes from './components/AllQuotes'
  export default {
    data() {
      return {
        quotes: []
      };
    },
    components: {
      progressBar: Header,
      newQuote: NewQuote,
      allQuotes: AllQuotes
    }

  }
</script>

<style>

</style>
