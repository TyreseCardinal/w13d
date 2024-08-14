<template>
  <div class="now-playing">
    <h2>Now Playing</h2>
    <div v-if="nowPlaying">
      <img :src="nowPlaying.image_url" alt="song cover" />
      <p>{{ nowPlaying.title }} by {{ nowPlaying.artist }}</p>
    </div>
    <div v-else>
      <p>No song is currently playing.</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ['nowPlaying']
}
</script>

<style scoped>
.now-playing {
  margin-top: 20px;
}

.now-playing h2 {
  font-size: 24px;
  margin-bottom: 10px;
}

.now-playing img {
  width: 100px;
  height: 100px;
  border-radius: 10px;
  margin-bottom: 10px;
}

.now-playing p {
  font-size: 20px;
  font-weight: bold;
}
</style>
