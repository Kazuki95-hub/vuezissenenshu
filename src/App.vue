<template>
  <div id="app">
    <input type="text" v-model= "number">
    <button @click= "serchAddress">住所自動入力</button>
    <p>Address：{{ jyusho }}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return{
      jyusho:""
    }
  },
  methods: {
    async serchAddress(){
      let address = await axios.get(`https://apis.postcode-jp.com/api/v4/postcodes/${this.number}?HLzIChi5hK02FZ8XOpCFGYFzmP0FJRb7UDFpUHS`);
      console.log(address.data[0].allAddress);
      this.jyusho =address.data[0].allAddress
    },
  }
};
</script>