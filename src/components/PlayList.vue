<template>
  <div class="playlist">
    <h2>PlayList</h2>
    <div v-if="playlist.length === 0">
      <p>No songs selected. Please pick a song from the list.</p>
    </div>
    <ul>
      <li v-for="song in playlist" :key="song.song_id" class="playlist-item">
        <div class="song-details">
          <img :src="song.image_url" alt="song cover" />
          <span>{{ song.title }} by {{ song.artist }}</span>
        </div>
        <button @click="playSong(song)" class="play-button">&#x25B6;</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ['playlist'],
  methods: {
    playSong(song) {
      this.$emit('song-played', song);
    }
  }
}
</script>

<style scoped>
.playlist {
  margin-bottom: 20px;
}

.playlist h2 {
  font-size: 24px;
  margin-bottom: 10px;
}

.playlist ul {
  list-style-type: none;
  padding: 0;
}

.playlist-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  margin-bottom: 10px;
  transition: background-color 0.3s ease;
}

.playlist-item:hover {
  background-color: #e0e0e0;
}

.song-details {
  display: flex;
  align-items: center;
}

.song-details img {
  width: 50px;
  height: 50px;
  margin-right: 10px;
  border-radius: 5px;
}

.song-details span {
  font-size: 18px;
}

.play-button {
  background-color: #274472;
  /* Primary color */
  border: none;
  color: white;
  font-size: 20px;
  padding: 10px;
  border-radius: 50%;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.2s ease;
}

.play-button:hover {
  background-color: #1c344f;
  transform: scale(1.1);
}

.play-button:active {
  transform: scale(0.95);
}

.play-button:focus {
  outline: none;
  box-shadow: 0 0 5px #274472;
}
</style>
