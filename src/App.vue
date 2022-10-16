<template>
  <main class="wrapper">
    <scoreboard-component />
  </main>
</template>

<script>
import ScoreboardComponent from '@/components/Scoreboard.vue';

export default {
  name: 'CrokinoleKeeper',
  components: {
    ScoreboardComponent,
  },
}
</script>

<style scoped lang="scss">
.wrapper {
  height: 100vh;
  width: 100vw;
}
</style>
