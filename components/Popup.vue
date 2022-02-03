<template>
  <div class="popup">
    <div class="bg"></div>
    <div class="container" v-click-outside="close">
      <span @click="close" id="closeX">X</span>
      <div class="text">
        <h2 class="ideaname">
          {{ name }}
        </h2>
        <p class="ideadesc">{{ desc }}</p>
        <span id="closeTxt">click anywhere outside to close this window</span>
      </div>
    </div>
  </div>
</template>

<style src="~/assets/styles/popup.css" scoped>
</style>

<script>
import vClickOutside from "v-click-outside";
export default {
  directives: {
    clickOutside: vClickOutside.directive,
  },
  props: {
    id: {
      type: Number,
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
  methods: {
    close() {
      this.$emit("onClose");
    },
  },
};
</script>
