<script>
import {store} from '../store'
import axios  from 'axios';

export default {
  data(){
    return{
      store,
    }
  },
  methods: {
    search(){
      console.log(this.store.searchText)

    axios.get(`https://api.themoviedb.org/3/search/movie?api_key=21113d2a59214cb58de84d087e9a0b2d&query=`, {
      params:{
        api_key: '21113d2a59214cb58de84d087e9a0b2d',
        query: this.store.searchText
      }
        }).then(response => {
          console.log(response.data)
          this.store.movies = response.data.results

      });
    }
  },
  props: {
  }
}
</script>

<template>
  <input v-model="store.searchText" type="text" placeholder="scrivi il titolo ">
  <button @click="search()">Cerca</button>
    <div class="container">
      <div class="row">
        <div class="col-4" v-for="(movie, i) in store.movies" :key="i"> 
          <div>
            {{ movie.title }}
          </div> 
          <div>
            {{ movie.original_title }}
          </div> 
          <div>
            {{ movie.original_language }}
          </div> 
          <div>
            {{ movie.vote_average}}
          </div>
          <hr>
        </div>
      </div>
      
    </div>
    
</template>


<style>

</style>