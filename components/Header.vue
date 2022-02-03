<template>
  <div class="header">
    <NuxtLink to="/" class="title"><h1>dump.</h1></NuxtLink>

    <div class="overlay" id="nav">
      <a href="javascript:void(0)" class="closebtn" @click="closeNav()"
        >&times;</a
      >

      <div class="nav">
        <NuxtLink to="/ideas">idea?</NuxtLink>
        <NuxtLink to="/about">about.</NuxtLink>
      </div>
    </div>

    <span @click="openNav()" id="openbtn">&#9776;</span>
  </div>
</template>

<style src="~/assets/styles/header.css">
</style>

<script>
export default {
  methods: {
    /* Open when someone clicks on the span element */
    openNav() {
      document.getElementById("nav").style.height = "100%";
    },

    /* Close when someone clicks on the "x" symbol inside the overlay */
    closeNav() {
      document.getElementById("nav").style.height = "0%";
    },
  },
};
</script>