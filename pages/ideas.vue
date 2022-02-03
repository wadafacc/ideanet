<template class="flex">
  <div>
    <Header />
    <div class="flex"><h3>ideas.</h3></div>
    <h3 v-if="$fetchState.pending" class="errorhandler flex">
      Loading Ideas...
    </h3>
    <h3 v-else-if="$fetchState.error" class="errorhandler flex">
      An Error occured while fetching ideas.
    </h3>
    <div class="ideas" v-else>
      <Idea
        v-for="idea in ideas"
        :key="idea._id"
        :name="idea.name"
        :desc="idea.desc"
        :id="idea._id"
        @popup="pppState = idea"
      />
    </div>
    <div v-if="pppState">
      <Popup
        @onClose="pppState = undefined"
        :name="pppState.name"
        :desc="pppState.desc"
        :id="pppState._id"
      />
    </div>
    <div class="flex">
      <NuxtLink to="/newIdea">got an idea?</NuxtLink>
    </div>
  </div>
</template>

<style scoped>
a {
  font-family: "Amatic SC", cursive;
  font-size: 3rem;
}
.errorhandler {
  font-size: 3rem;
  margin: 2rem;
}
</style>

<script>
export default {
  name: "IdeasPage",
  head() {
    return {
      title: "idea | ideas.",
    };
  },
  data() {
    return {
      pppState: undefined,
      ideas: [],
    };
  },
  async fetch() {
    this.ideas = await fetch("https://ideanetapi.herokuapp.com/getIdeas", {
      mode: "cors",
    }).then((res) => res.json());
  },
};
</script>
