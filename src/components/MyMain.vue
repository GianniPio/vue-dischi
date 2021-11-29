<template>
  <main>
    <div>
      <Search @changeSelect="changeGen"/> <!-- tramite $emit il padre capice che deve attivare il metodo selezionato -->
    </div>

    <div v-if="listadischi.length == 0">
      <Load/>
    </div>

    <div v-else id="container">
      <MyDisc v-for="disco, i in filtraDischi" :key="i" :details="disco"/> <!-- sostituire il nome della lista, con quello del computed -->
      
    </div>
      
  </main>
</template>

<script>

import Load from "@/components/Load.vue";
import MyDisc from "@/components/MyDisc.vue";
import axios from "axios"; // importo axios
import Search from "@/components/Search.vue";


export default {
  name: "MyMain",
  components: {
    MyDisc,
    Load,
    Search,
  },
  data() {
    return {
      apiURL: "https://flynn.boolean.careers/exercises/api/array/music", //link per prendere i dati dell'array dall'esterno
      listadischi: [], // array vuoto, in cui viene salvato successivamente l'array esterno
      optionSelect:"", // elemento dell'option
    }
  },
  created() {
    this.getDischi();
  },


  methods: {
    getDischi() {
      axios.get(this.apiURL).then((result) => {this.listadischi = result.data.response;}) //tramite axios, prendiamo il link esterno, e poi lo salviamo nell'array vuoto
    },

    changeGen(event) {
      this.optionSelect = event.target.value // la variabile assume il valore della option del figlio
    }
  },

  computed: {
    filtraDischi() {
      if(this.optionSelect === "all") {
        return this.listadischi  // se 'loption è all, stampa l'intera lista
      }
      return this.listadischi.filter((elem) =>{
        return elem.genre.toLowerCase().includes(this.optionSelect.toLowerCase()) // altrimenti stampa la lista che contiene l'option
      }) 
       
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
          display: flex;
          justify-content: space-around;
          flex-wrap: wrap;
        }
    }

</style>
