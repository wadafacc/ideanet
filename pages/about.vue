<template class="flex">
  <Header />
</template>



<script>
export default {
  name: "AboutPage",
  head() {
    return {
      title: "idea | about.",
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: "description",
          name: "description",
          content: "My custom description",
        },
      ],
    };
  },
};
</script>
