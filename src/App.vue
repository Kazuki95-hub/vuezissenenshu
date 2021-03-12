<template>
  <div id="app">
    <input type="text" v-model= "number">
    <button @click= "serchAddress">住所自動入力</button>
    <p>Address：{{ address }}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return{
      number:""
    }
  },
  methods: {
    serchAddress(){
      
    },
    created(){
      axios.get(`https://apis.postcode-jp.com/api/v4/postcodes/${this.address}/HLzIChi5hK02FZ8XOpCFGYFzmP0FJRb7UDFpUHS`)
      .then()
    }
  }
};
</script>