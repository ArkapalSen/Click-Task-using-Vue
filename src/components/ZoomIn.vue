<template>
  <div>
    <button @click="zoomInData">+</button>
  </div>
</template>

<script>
export default {
  name: "ZoomIn",
  props: {
    size: String,
  },
  data() {
    return {};
  },
  methods: {
    zoomInData() {
      let mutateSize = this.size;
      mutateSize++;
      mutateSize = `${mutateSize}px`;
      this.$emit("update-Insize", mutateSize);
    },
  },
};
</script>

<style>
</style>