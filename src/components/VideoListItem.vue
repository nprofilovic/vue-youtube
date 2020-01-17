<template>
  <li class="list-group-item media">
    <img :src="thumbnailUrl" class="mr-3" />
    <div class="media-body">
      <h5 class="mt-0 mb-1">{{ video.snippet.title }}</h5 >
      {{video.snippet.description}}
    </div>
  </li>
</template>

<script>
export default {
  name: 'VideoListItem',
  props: ['video'],

  computed: {
    thumbnailUrl() {
      return this.video.snippet.thumbnails.default.url
    }
  }
}
</script>

<style>

</style>