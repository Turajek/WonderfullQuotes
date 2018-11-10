<template>
  <div class="row">
    <div class="col-sm-12 form group">
      <label>New Quote</label>
      <textarea class="form-control" rows="3" v-model="quote"></textarea>
    </div>
    <div class="col-sm-12 text-center">
      <button class="btn btn-primary" @click="createNew">Add Quote</button>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      quote: ''
    }
  },
  methods:{
    createNew(){
      this.$emit('quoteAdded',this.quote);
      this.quote = '';
    }
  }

}

</script>

<style scoped>
  .col-sm-12 {
    margin: 10px;
  }
</style>
