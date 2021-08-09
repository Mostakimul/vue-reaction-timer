<template>
  <div class="box" v-if="showBlock" @click="stopTimer">
    <h2>React Now!!!</h2>
  </div>
</template>

<script>
export default {
  props: {
    delay: {
      type: Number,
      default: 3000,
    },
  },
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      // console.log(this.delay);
      this.startTimer();
    }, this.delay);
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.timer);
      // console.log(this.reactionTime);
    },
  },
  // updated() {
  //   console.log('updated block');
  // },
  // unmounted() {
  //   console.log('unmounted');
  // },
};
</script>

<style lang="scss" scoped>
.box {
  width: 40rem;
  background: crimson;
  color: aliceblue;
  text-align: center;
  padding: 10rem 0;
  margin: 4rem auto;
  border-radius: 1.5rem;
}
</style>
