<template>
  <main class="container">
    <section>
      <h1>Ninja Reaction Timer</h1>
      <button @click="start" :disabled="isPlaying">play</button>
      <BlockComponent v-if="isPlaying" :delay="delay" @end="endGame" />
      <ResultComponent v-if="showResults" :score="score" />
    </section>
  </main>
</template>

<script>
import BlockComponent from "./components/Block-component.vue";
import ResultComponent from "./components/Results-component.vue";
export default {
  name: "App",
  components: { BlockComponent, ResultComponent },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
    };
  },
  methods: {
    start() {
      this.delay = 1500 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResults = false;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResults = true;
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
