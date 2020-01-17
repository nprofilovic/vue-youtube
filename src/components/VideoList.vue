<template>
  <div>
    <ul class="list-group list-unstyled">
      <VideoListItem v-for="video in videos" :key="video.etag" :video="video"/>  
    </ul>
  </div>
</template>

<script>
import VideoListItem from './VideoListItem'

export default {
  name: 'VideoList',
  components: {
    VideoListItem
  },
  props: ['videos'],
}


</script>

<style>

</style>