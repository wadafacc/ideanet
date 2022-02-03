<template>
  <div>
    <Header />
    <div class="flex">
      <h3>hello!</h3>
    </div>
    <div class="flex">
      <div class="about">
        <h4>
          thanks for visiting, means a lot to me. if you're curious on why this
          thing exists, <br />here's the short answer:
          <b>i tend to forget my ideas.</b><br />
          thats why i created this place so people could store <i>and</i> share
          them! there's no validation as i believe in the good in humanity, so
          please don't fill it with shit.<br />
          <i>thanks in advance.</i>
        </h4>
      </div>
    </div>
  </div>
</template>

<style src="~/assets/styles/about.css" scoped>
</style>

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
