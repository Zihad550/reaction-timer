<template>
  <h1>Reaction timer</h1>
  <button @click="startGame" :disabled="isPlaying">Start</button>
  <Block :delay="delay" v-if="isPlaying" />
</template>

<script>
import Block from "./components/Block.vue";

export default {
  name: "App",
  components: {
    Block,
  },
  data() {
    return {
      delay: null,
      isPlaying: false,
    };
  },
  methods: {
    startGame() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      console.log(this.delay, this.isPlaying);
    },
  },
};
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
