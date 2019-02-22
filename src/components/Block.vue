<template>
  <div class="block-container">{{block.status}}</div>
</template>

<script>
export default {
  name: "Block",
  props: ["block"]
};
</script>

<style>
.block-container {
  padding: 0;
  margin: 0;
  width: 4em;
  height: 4em;
  border: 2px;
  border-style: solid;
  background-color: red;
}
</style>
