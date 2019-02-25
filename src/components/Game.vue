<template>
  <div class="game-container">
    <span v-for="(el, index) in grid" :key="index">
      <Row v-bind:blocks="el" v-bind:blockClicked="blockClicked"/>
    </span>
  </div>
</template>

<script>
import Row from "./Row.vue";

export default {
  name: "Game",
  components: {
    Row
  },
  props: ["rowLength"],
  watch: {
    rowLength() {
      this.updateGrid();
    }
  },
  methods: {
    updateGrid: function() {
      let buildingGrid = [];
      let total = this.rowLength;

      if (total > 14) {
        total = 14;
      }
      if (total < 0) {
        total = 0;
      }

      for (let i = 1; i <= total; i++) {
        let row = [];
        for (let j = 1; j <= total; j++) {
          row.push({ id: String(i) + "-" + String(j), status: undefined });
        }
        buildingGrid.push(row);
      }

      this.grid = buildingGrid;
    },
    blockClicked(rowCol) {
      let arr = rowCol.split("-");
      let row = Number(arr[0]) - 1;
      let col = Number(arr[1]) - 1;

      this.grid[row][col] = "X";
    }
  },
  created: function() {
    this.updateGrid();
  },
  data() {
    return {
      grid: undefined
    };
  }
};
</script>

<style>
.game-container {
  margin-top: -2em;
}
</style>
