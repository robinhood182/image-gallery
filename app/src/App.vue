<template>
  <div id="app">
    <h1>Petfolio</h1>
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
body {
  font-family: 'Source Sans Pro', sans-serif;
}

h1 {
  font-family: 'Economica', sans-serif;
}
</style>
