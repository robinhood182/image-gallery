<template>
  <div id="app">
    <h1>Image Gallery</h1>
    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
      <router-link to="/albums">Albums</router-link>
    </nav>
    <router-view/>
  </div>
</template>

<script>

export default {

};
</script>

<style>

</style>
