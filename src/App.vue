<template>
  <main class="container">
    <section>
      <h1>Ninja Reaction Timer</h1>
      <button @click="start" :disabled="isPlaying">play</button>
      <BlockComponent v-if="isPlaying" :delay="delay" @end="endGame" />
      <p>Reaction time: {{ score }}</p>
    </section>
  </main>
</template>

<script>
import BlockComponent from "./components/Block-component.vue";
export default {
  name: "App",
  components: { BlockComponent },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
    },
  },
};
</script>

<style>
h1 {
  text-align: center;
  padding-top: 15px;
}
</style>
