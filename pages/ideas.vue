<template class="flex">
  <div>
    <Header />
    <div class="flex"><h3>ideas.</h3></div>
    <div class="ideas">
      <Idea
        v-for="idea in ideas"
        :key="idea.id"
        :name="idea.name"
        :desc="idea.desc"
        :id="idea.id"
        @popup="pppState = idea"
      />
    </div>
    <div v-if="pppState">
      <Popup
        @onClose="pppState = undefined"
        :name="pppState.name"
        :desc="pppState.desc"
        :id="pppState.id"
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
    };
  },
  asyncData() {
    return {
      ideas: [
        {
          name: "this is an actual filler title for an idea.",
          desc: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Adipiscing bibendum est ultricies integer quis. Tellus integer feugiat scelerisque varius morbi enim. Lectus nulla at volutpat diam. Pulvinar mattis nunc sed blandit. Placerat orci nulla pellentesque dignissim. Ultrices sagittis orci a scelerisque. Aenean et tortor at risus viverra adipiscing at in tellus. Nisl nunc mi ipsum faucibus vitae aliquet nec ullamcorper sit. Enim ut tellus elementum sagittis. Non odio euismod lacinia at quis risus. Sed adipiscing diam donec adipiscing tristique risus nec. Ut tristique et egestas quis ipsum suspendisse ultrices gravida dictum. Quis varius quam quisque id diam vel quam.",
          id: 1,
        },
        {
          name: "wadawa dadadada",
          desc: "wahfwuoiafbwub woadu bnwd ouaib d",
          id: 2,
        },
        {
          name: "rfgzhjukztt",
          desc: "wahfwuoiafbwub woadu bnwd ouaib d",
          id: 3,
        },
        {
          name: "rfgzhjukztt",
          desc: "wahfwuoiafbwub woadu bnwd ouaib d",
          id: 3,
        },
        {
          name: "rfgzhjukztt",
          desc: "wahfwuoiafbwub woadu bnwd ouaib d",
          id: 3,
        },
        {
          name: "rfgzhjukztt",
          desc: "wahfwuoiafbwub woadu bnwd ouaib d",
          id: 3,
        },
        {
          name: "rfgzhjukztt",
          desc: "wahfwuoiafbwub woadu bnwd ouaib d",
          id: 3,
        },
        {
          name: "rfgzhjukztt",
          desc: "wahfwuoiafbwub woadu bnwd ouaib d",
          id: 3,
        },
        {
          name: "rfgzhjukztt",
          desc: "wahfwuoiafbwub woadu bnwd ouaib d",
          id: 3,
        },
        {
          name: "rfgzhjukztt",
          desc: "wahfwuoiafbwub woadu bnwd ouaib d",
          id: 3,
        },
        {
          name: "rfgzhjukztt",
          desc: "wahfwuoiafbwub woadu bnwd ouaib d",
          id: 3,
        },
        {
          name: "rfgzhjukztt",
          desc: "wahfwuoiafbwub woadu bnwd ouaib d",
          id: 3,
        },
        {
          name: "rfgzhjukztt",
          desc: "wahfwuoiafbwub woadu bnwd ouaib d",
          id: 3,
        },
        {
          name: "rfgzhjukztt",
          desc: "wahfwuoiafbwub woadu bnwd ouaib d",
          id: 3,
        },
        {
          name: "rfgzhjukztt",
          desc: "wahfwuoiafbwub woadu bnwd ouaib d",
          id: 3,
        },
        {
          name: "rfgzhjukztt",
          desc: "wahfwuoiafbwub woadu bnwd ouaib d",
          id: 3,
        },
        {
          name: "rfgzhjukztt",
          desc: "wahfwuoiafbwub woadu bnwd ouaib d",
          id: 3,
        },
      ],
    };
  },
};
</script>
