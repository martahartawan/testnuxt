<template>
  <div class="container">
    <AppHeader/>
    <App v-for="app in apps" :key="app.id" :id="aplikasi.id" :aplikasi="aplikasi.aplikasi"/>
    <nuxt/>
  </div>
</template>

<script>
import AppHeader from "../components/AppHeader";
import axios from "axios";
import App from "../components/App";


export default {
  components: {
    AppHeader,
    App
  },
  data(){ 
    return{
      apps:[]
    };
  },
  async created(){
    const config = {
      header: {
        Accept: "aplication/json"
      }
    };
    try {
      const res = await axios.get("https://6283bcbc38279cef71dbafbe.mockapi.io/aplikasi",config);
      this.apps = res.data.results;

    } catch (err) {
      console.log(err);
    }
  }
};
</script>


<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1rem;
  line-height: 1.6;
  background: #f4f4f4;
}

a {
  color: #666;
  text-decoration: none;
}

ul {
  list-style: none;
}

.container {
  max-width: 800px;
  margin: 2rem auto;
  overflow: hidden;
  padding: 1rem 2rem;
  background: #fff;
}
</style>