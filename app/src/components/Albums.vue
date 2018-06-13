<template>
  <div>
    <h1>Albums</h1>
    <ul v-if="albums">
      <li
        v-for="album in albums"
        :key="album.id"
      >
        <router-link :to="`/albums/${album.id}`">
          {{ album.title }}
        </router-link>
      </li>
    </ul>
    <router-link :to="`/albums/new`">Add New Album</router-link>
  </div>
</template>

<script>
import { getAlbums } from '../services/api';

export default {
  data() {
    return {
      albums: null,
      adding: false
    };
  },
  created() {
    getAlbums()
      .then(albums => {
        this.albums = albums;
      });
  }
};
</script>

<style scoped>
  div { 
    display: flex;
    flex-flow: column nowrap;
    align-items: center;
  }

  li {
    list-style: none;
    margin: 10px;
    text-align: center;
  }
</style>

