<template>
  <div class="player" :class="{'black': color === 'black', 'white': color === 'white', 'natural': color === 'natural', 'darkbrown': color === 'darkbrown'}">
    <div class="score">
      {{ score }}
    </div>
    <div class="buttons">
      <button
        @click="increment"
        aria-label="increment score by 5"
        class="button"
      />
      <button
        @click="decrement"
        aria-label="decrement score by 5"
        class="button"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Player',
  props: [
    'color'
  ],
  data: () => ({
    score: 0,
    minScore: 0,
  }),
  methods: {
    increment() {
      this.score += 5;
    },
    decrement() {
      this.score > 0 ? this.score -= 5 : null;
    },
  }
}
</script>

<style scoped lang="scss">
.player {
  $white: #fff;
  $black: #111;
  $natural: #e6ab85;
  $darkbrown: #3a2114;

  position: relative;
  display: grid;
  place-items: stretch;
  background-color: var(--primary);

  &.black {
    --primary: #{$black};
    --score: #{$white};
  }

  &.white {
    --primary: #{$white};
    --score: #{$black};
  }

  &.natural {
    --primary: #{$natural};
    --score: #{$black};
  }

  &.darkbrown {
    --primary: #{$darkbrown};
    --score: #{$white};
  }

  //.score,
  //.buttons {
  //  grid-column: 1;
  //  grid-row: 1;
  //}

  .score {
    grid-column: 1;
    grid-row: 1;
    place-self: center;
    font-size: 50vh;
    line-height: 1;
    color: var(--score);
    text-shadow: 0 0.25rem 0.5rem var(--text-shadow);
  }

  .buttons {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    display: grid;
    grid-template-rows: repeat(2, 1fr);
    place-items: stretch;

    .button {
      padding: 0;
      border: 0;
      border-radius: 0;
      background-color: transparent;

      &:hover {
        background-color: rgba(0, 0, 0, .5);
      }

      &:focus {
        outline: none;
      }
    }
  }
}
</style>
