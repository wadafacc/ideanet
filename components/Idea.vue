<template>
  <div class="container" @click="$emit('popup')">
    <h2 class="ideaname">{{ name }}</h2>
  </div>
</template>

<style src="~/assets/styles/container.css" scoped>
</style>

<script>
export default {
  props: {
    id: {
      type: String,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    desc: {
      type: String,
    },
  },
};
</script>
