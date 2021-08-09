<template>
  <div class="container">
    <h1>Hello from vue and vite!!!</h1>

    <button @click="play" :disabled="isPlaying">Play</button>

    <Block v-if="isPlaying" :delay="delay" />
  </div>
</template>

<script>
import Block from './components/Block.vue';
export default {
  name: 'App',
  components: {
    Block,
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
    };
  },
  methods: {
    play() {
      this.delay = 3000 + Math.random() * 7000;
      this.isPlaying = true;
      // console.log(typeof this.delay);
    },
  },
};
</script>

<style lang="scss" scoped>
.container {
  text-align: center;
}
.container h1 {
  color: #5a5a5a;
  font-size: 3rem;
  margin-top: 4rem;
}
.container button,
.container button:focus {
  outline: none;
  border: none;
  padding: 1rem 2.5rem;
  margin: 1.5rem;
  color: aliceblue;
  background: crimson;
  font-weight: bold;
  font-size: 1.6rem;
  border-radius: 0.7rem;
  cursor: pointer;
}
.container button:disabled {
  background: #dc143c5d;
  color: #f0f8ff4d;
  cursor: not-allowed;
}
</style>
