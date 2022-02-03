<template>
  <div>
    <Header />
    <form action="" method="post" v-on:submit.prevent="onSubmit()">
      <input
        type="text"
        name="ideaname"
        id="name"
        placeholder="your idea."
        v-model="name"
        required
      />
      <input
        type="text"
        name="ideadesc"
        id="desc"
        placeholder="description."
        v-model="desc"
        required
      />
      <input type="submit" value="submit" />
    </form>
  </div>
</template>

<script>
import axios from "axios";
export default {
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
        .post(
          "https://getform.io/f/{unique-endpoint-generated-on-step-1}",
          data,
          {
            headers: {
              Accept: "application/json",
            },
          }
        )
        .then(
          (response) => {
            this.isSuccess = response.data.success ? true : false;
          },
          (response) => {
            // Error
          }
        );
    },
  },
  head() {
    return {
      title: "idea | idea?",
    };
  },
};
</script>
