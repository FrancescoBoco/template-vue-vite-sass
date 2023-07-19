

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import Footer from './components/Footer.vue';
import axios  from 'axios';
import {store} from '../src/store.js'


export default {
  name: "App",
  components:{
    Header,
    Main,
    Footer,
  },
  data(){
    return{
        store,
    }
  },
  methods: {

  },
//   created(){
//     axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0', {
//         
//     }).then(response => {

//       });
    };
</script>

<template>
  <Header />

  <Main/>
   

  <Footer/>
</template>

<style lang="scss" >
@use "./assets/scss/main.scss";
</style>
