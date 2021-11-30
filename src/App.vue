<template>
  <div id="app">
    <MyHeader @changeSelect="changeGen"/> <!-- attiva la funzione changeGen -->
    <MyMain :selectedGen="optionSelect"/> <!-- prende la variabile optionSelect e la trasferisce nel main tramite la prop selectedGen -->
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
     changeGen(event) { // una volta attivata, prende il valore del selected e lo salva in optionSelect
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
