<template>
  <div id="app">
    <img src="./assets/logo.png">
    <HelloWorld/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Vue from 'vue'
import axios from 'axios';
import VueAxios from 'vue-axios';
Vue.use(axios,VueAxios);

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  created() {
    const api = `${process.env.APIPATH}/api/${process.env.CUSTOMPATH}/products`; // 'http://localhost:3000/api/casper/products';
    // API 伺服器路徑
    // 所申請的 APIPath
    console.log(process.env.APIPATH, process.env.CUSTOMPATH);
    this.$http.get(api).then((response) => {
      console.log(response.data);
    });
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
