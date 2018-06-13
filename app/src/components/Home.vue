<template>
  <div id="home">
    <img src="https://i.imgur.com/l0t8axs.jpg">
    <section class="home-text">
      <h1>Commemorate the ones you love</h1>
      <router-link to="/albums/new"><button>Get Started</button></router-link>
    </section>
    <ul v-if="stats">
      <li>Total albums: {{stats.count}}</li>
      <li>Average memories per album: {{parseInt(stats.avg)}}</li>
      <li>Least amount of memories per album: {{stats.min}}</li>
      <li>Most amount of memories per album: {{stats.max}}</li>
    </ul>
  </div>
</template>

<script>
import { getStats } from '../services/api';

export default {

  data() {
    return {
      stats: null
    };
  },

  created() {
    getStats() 
      .then(stats => {
        this.stats = stats;
      });
  }
};
</script>

<style scoped>
#home {
  padding: 100px 0px;
  display: flex;
  align-items: center;
}

h1 {
  margin: 50px;
}

.home-text {
  text-align: center;
}

img {
  width: 40%;
  border-radius: 25px;
}
</style>

