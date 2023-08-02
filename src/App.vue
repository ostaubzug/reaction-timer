<template>
  <main class="container">
    <section>
      <h1>Ninja Reaction Timer</h1>
      <button @click="start">play</button>
    </section>
  </main>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      isPlaying: false,
      delay: null,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      console.log(this.delay);
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
