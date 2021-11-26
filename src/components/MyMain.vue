<template>
  <main>

    <div v-if="listadischi.length == 0">
      <Load/>
    </div>

    <div v-else id="container">
      <MyDiscs v-for="disco, i in listadischi" :key="i" :details="disco"/>
      
    </div>
      
  </main>
</template>

<script>

import Load from "@/components/Load.vue";
import MyDiscs from "@/components/MyDiscs.vue";
import axios from "axios";


export default {
  name: "MyMain",
  components: {
    MyDiscs,
    Load,
  },
  data() {
    return {
      apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
      listadischi: [],
    }
  },
  created() {
    this.getDischi();
  },
  methods: {
    getDischi() {
      axios.get(this.apiURL).then((result) => {this.listadischi = result.data.response;})
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

    main {
        background-color: #1e2d3b;
        height: 100%;

        #container {
          width: 70%;
          margin: 0 auto;
          padding-top: 20px;
          display: flex;
          justify-content: space-around;
          flex-wrap: wrap;
        }
    }

</style>
