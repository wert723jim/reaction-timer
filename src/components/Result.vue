<template>
  <p>Your reaction time is {{ score }} ms</p>
  <p>{{ rank }}</p>
</template>

<script>
export default {
  props: ['score'],
  data() {
    return {
      rank: null
    }
  },
  mounted() {
    if (this.score < 250) {
      this.rank = 'nice'
    } else if (this.score < 400) {
      this.rank = 'normal'
    } else {
      this.rank = 'slow'
    }
  }
}
</script>

<style>

</style>