<template>
    <div class="container">
      <appHeader :quotesCount="quotes.length" :maxQuotes="maxQuotes"></appHeader>
      <appNewQuote @quoteAdded="addQuote"></appNewQuote>
      <appQuoteGrid @quoteDeleted="deleteQuote":quotes="quotes"></appQuoteGrid>
      <appInfoBox></appInfoBox>
    </div>
</template>

<script>
    import NewQuote from './components/NewQuote.vue';
    import QuoteGrid from './components/QuoteGrid.vue';
    import InfoBox from './components/InfoBox.vue';
    import Header from './components/Header.vue';
    export default {
      data: function() {
        return {
          maxQuotes: 10,
          quotes: ['test quote','test quote2']
        }
      },
      components: {
        appQuoteGrid: QuoteGrid,
        appNewQuote: NewQuote,
        appInfoBox: InfoBox,
        appHeader: Header
      },
      methods: {
        addQuote(quote){
          if (this.quotes.length >= this.maxQuotes) {
            alert('Delete some quote first')
          } else {
          this.quotes.push(quote);
        }
        },
        deleteQuote(index){
          this.quotes.splice(index,1);
        }
      }

    }
</script>

<style>
</style>
