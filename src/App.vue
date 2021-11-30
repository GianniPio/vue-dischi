<template>
  <div id="app">
    <MyHeader @changeSelect="changeGen"/>
    <MyMain :selectedGen="optionSelect"/>
  </div>
</template>

<script>
import MyHeader from "./components/MyHeader.vue";
import MyMain from "./components/MyMain.vue";

export default {
  name: "App",
  components: {
    MyHeader,
    MyMain,
  },

  data() {
    return {
      optionSelect:"", // elemento dell'option
    }
  },

  methods: {
     changeGen(event) {
      this.optionSelect = event.target.value
    }
  }


};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100vh;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
