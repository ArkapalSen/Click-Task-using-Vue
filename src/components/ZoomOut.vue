<template>
  <div>
    <button @click="zoomOutData">-</button>
  </div>
</template>

<script>
export default {
  name: "ZoomOut",
  props: {
    size: String,
  },
  data() {
    return {};
  },
  methods: {
    zoomOutData() {
      let mutateSize = this.size;
      mutateSize = mutateSize - 1;
      console.log(mutateSize);
      mutateSize = `${mutateSize}px`;
      this.$emit("update-Outsize", mutateSize);
    },
  },
};
</script>

<style>
</style>