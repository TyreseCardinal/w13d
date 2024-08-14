<template>
  <div id="app" class="app-container">
    <SongList :songs="songs" @song-selected="addToPlaylist" />
    <PlayList :playlist="playlist" @song-played="setNowPlaying" />
    <NowPlaying :nowPlaying="nowPlaying" />
  </div>
</template>

<script>
import SongList from './components/SongList.vue'
import PlayList from './components/PlayList.vue'
import NowPlaying from './components/NowPlaying.vue'

export default {
  components: {
    SongList,
    PlayList,
    NowPlaying
  },
  data() {
    return {
      songs: [
        { title: 'Song 1', artist: 'Artist 1', song_id: 1, image_url: 'https://picsum.photos/200/300?random=1' },
        { title: 'Song 2', artist: 'Artist 2', song_id: 2, image_url: 'https://picsum.photos/200/300?random=2' },
        { title: 'Song 3', artist: 'Artist 3', song_id: 3, image_url: 'https://picsum.photos/200/300?random=3' },
        { title: 'Song 4', artist: 'Artist 4', song_id: 4, image_url: 'https://picsum.photos/200/300?random=4' },
        { title: 'Song 5', artist: 'Artist 5', song_id: 5, image_url: 'https://picsum.photos/200/300?random=5' },
        { title: 'Song 6', artist: 'Artist 6', song_id: 6, image_url: 'https://picsum.photos/200/300?random=6' }
      ],
      playlist: [],
      nowPlaying: null
    }
  },
  methods: {
    addToPlaylist(song) {
      this.playlist.push(song);
    },
    setNowPlaying(song) {
      this.nowPlaying = song;
    }
  }
}
</script>

<style>
.app-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  font-family: Arial, sans-serif;
  background-color: #f7f7f7;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

h2 {
  color: #274472;
  /* Primary color */
}

p {
  color: #555;
}

ul {
  padding: 0;
}

li {
  list-style: none;
}
</style>
