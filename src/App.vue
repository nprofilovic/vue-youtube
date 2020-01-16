<template>
  <div id="app">
    <SearchBar @termChange="onTermChange" />
    <VideoList />
  </div>
</template>

<script>
import axios from 'axios'
import SearchBar from './components/SearchBar'
import VideoList from './components/VideoList'
const API_KEY = 'AIzaSyCbO3Z1BAuLheDTh-T_DsnO1E4CbP0at5Q'

export default {
  name: 'App',
  components: {
    SearchBar,
    VideoList
  },

  methods: {
    onTermChange(searchTerm) {  
      axios.get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          key: API_KEY,
          type: 'video',
          part: 'snippet',
          q: searchTerm
        }
      })
      .then(response => console.log(response))
     }
  }
  
}
</script>

<style>

</style>
