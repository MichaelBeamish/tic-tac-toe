<template>
  <div class="block-container" v-on:click="blockClicked(block.id)">
    <p class="xoxo">{{block.status}}</p>
  </div>
</template>

<script>
export default {
  name: "Block",
  props: ["block", "blockClicked"]
};
</script>

<style>
.block-container {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0;
  margin: 0;
  width: 4em;
  height: 4em;
  border: 2px;
  border-style: solid;
  background-color: red;
}

.xoxo {
  font-size: 3em;
}
</style>
