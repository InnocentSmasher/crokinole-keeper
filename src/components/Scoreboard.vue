<template>
  <div class="scoreboard">
    <player-component color="white" :key="game" />
    <player-component color="black" :key="game" />
    <button @click="resetGame" class="btn-reset">
      <icon-reset />
    </button>
  </div>
</template>

<script>
import IconReset from '@/components/icons/IconReset.vue';
import PlayerComponent from '@/components/Player.vue';

export default {
  name: 'Scoreboard',
  components: {
    IconReset,
    PlayerComponent,
  },
  data: () => ({
    game: 0,
  }),
  methods: {
    resetGame() {
      this.game++;
    },
  }
}
</script>

<style scoped lang="scss">
.scoreboard {
  position: relative;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  height: 100%;

  .btn-reset {
    position: absolute;
    height: 10vh;
    width: 10vh;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    line-height: 0;
    background-color: rgba(255, 255, 255, 0.9);
    color: #000;
    border-radius: 5vh;
    border: 0;
    box-shadow: 0 0.125rem 0.5rem rgba(0, 0, 0, 0.25);
  }
}
</style>
