<template>
  <div class="row-container">
    <span v-for="(block, index) in blocks" :key="index">
      <Block v-bind:block="block" v-bind:blockClicked="blockClicked"/>
    </span>
  </div>
</template>

<script>
import Block from "./Block.vue";

export default {
  name: "Row",
  components: {
    Block
  },
  props: ["blocks", "blockClicked"]
};
</script>

<style>
.row-container {
  padding: 0;
  margin: 0;
  display: flex;
  justify-content: center;
  background-color: green;
}
</style>
