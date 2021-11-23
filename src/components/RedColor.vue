<template>
  <div>
    <button @click="getData(color)">Red</button>
  </div>
</template>

<script>
export default {
  name: "RedColor",
  data() {
    return {
      color: "red",
    };
  },
  props:{
    getData : Function
  }
};
</script>

<style>
</style>