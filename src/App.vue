<template>
  <div id="app">
    <input type="text" v-model= "address">
    <button @click= "serchAddress">住所自動入力</button>
    <p>Address：{{ address }}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return{
      item:[{ allAddress:"value"}]
    }
  },
  methods: {
    async serchAddress(){
      let address = await axios.get(`https://apis.postcode-jp.com/api/v4/postcodes/${this.number}?HLzIChi5hK02FZ8XOpCFGYFzmP0FJRb7UDFpUHS`);
      console.log(address);
    },
  }
};
</script>