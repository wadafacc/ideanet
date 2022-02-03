<template>
  <div>
    <Header />
    <h3 class="flex">idea for an idea?</h3>
    <div class="flex">
      <form action="" method="post" v-on:submit.prevent="onSubmit()" id="frm">
        <input
          type="text"
          name="ideaname"
          id="name"
          placeholder="your idea."
          v-model="name"
          required
        />
        <textarea
          name="ideadesc"
          id="desc"
          placeholder="description."
          v-model="desc"
          required
          cols="60"
          rows="10"
          form="frm"
        ></textarea>
        <input type="submit" value="submit" />
      </form>
    </div>
    <div class="flex">
      <h4 v-if="success"><i>idea uploaded!</i></h4>
    </div>
  </div>
</template>

<style src="~/assets/styles/form.css" scoped>
</style>

<script>
import axios from "axios";
export default {
  data() {
    return {
      success: false,
    };
  },
  props: {
    name: {
      type: String,
      required: true,
    },
    desc: {
      type: String,
      required: true,
    },
  },
  methods: {
    onSubmit() {
      let data = {
        name: this.name,
        desc: this.desc,
      };
      axios
        .post("http://localhost:6969/createIdea", data, {
          headers: {
            Accept: "application/json",
          },
        })
        .then((res) => {
          console.log(res);
          this.success = res.data.success ? true : false;
        });
    },
  },
  head() {
    return {
      title: "idea | idea?",
    };
  },
};
</script>
