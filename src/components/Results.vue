<template>
  <div>
    <p>Reaction time: {{ score }}ms</p>
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
};
</script>

<style lang="scss" scoped></style>
