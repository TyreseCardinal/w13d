<template>
  <div class="song-list">
    <h2>Song List</h2>
    <ul>
      <li v-for="song in songs" :key="song.song_id" class="song-item">
        <img :src="song.image_url" alt="song cover" />
        <span>{{ song.title }} by {{ song.artist }}</span>
        <button @click="selectSong(song)">Add to playlist</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ['songs'],
  methods: {
    selectSong(song) {
      this.$emit('song-selected', song);
    }
  }
}
</script>

<style scoped>
.song-list {
  margin-bottom: 20px;
}

.song-list h2 {
  font-size: 24px;
  margin-bottom: 10px;
}

.song-list ul {
  list-style-type: none;
  padding: 0;
}

.song-item {
  display: flex;
  align-items: center;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  margin-bottom: 10px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.song-item:hover {
  background-color: #f0f0f0;
}

.song-item img {
  width: 50px;
  height: 50px;
  margin-right: 10px;
  border-radius: 5px;
}

.song-item span {
  font-size: 18px;
}

button {
  width: auto;
  height: fit-content;
  margin: 1rem 2rem;
  display: grid;
  justify-self: end;
}
</style>
