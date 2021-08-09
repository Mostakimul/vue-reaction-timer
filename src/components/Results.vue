<template>
  <div>
    <p>Reaction time: {{ score }}ms</p>
    <p class="rank">{{ rank }}</p>
  </div>
</template>

<script>
export default {
  props: {
    score: {
      type: Number,
      default: 0,
    },
  },
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score < 200) {
      this.rank = 'You are on firrreee!!!';
    } else if (this.score < 400) {
      this.rank = 'You are fassssst!!!';
    } else {
      this.rank = 'You are good!!!';
    }
  },
};
</script>

<style lang="scss" scoped>
.rank {
  font-size: 2rem;
  color: crimson;
  font-weight: bold;
}
</style>
