<template>
  <div id="app">
    <label>Row Size:
      <small>(up to 14)</small>
    </label>
    <br>
    <input type="text" placeholder="Please enter row length." v-model="rowLength">
    <div class="game">
      <Game v-bind:rowLength.sync="rowLength"/>
    </div>
  </div>
</template>

<script>
import Game from "./components/Game.vue";

export default {
  name: "app",
  components: {
    Game
  },
  data() {
    return {
      rowLength: 3
    };
  }
};
</script>

<style>
body {
  background-color: lightgray;
}
.game {
  display: flex;
  justify-content: center;
}
</style>
