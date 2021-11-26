<template>
  <main>
      <div id="container">
        <MyDiscs/>
      </div>
  </main>
</template>

<script>

import MyDiscs from "@/components/MyDiscs.vue";

export default {
  name: "MyMain",
  components: {
    MyDiscs
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

    main {
        background-color: #1e2d3b;
        height: auto;

        #container {
            width: 70%;
            margin: 0 auto;
            padding: 20px 0;
            border: 1px solid white;
        }
    }

</style>
