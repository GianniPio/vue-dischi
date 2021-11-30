<template>
  <main>

    <!-- Fase di caricamento dei dati -->
    <div>
     <div v-if="listadischi.length == 0">
      <Load/>
    </div>
    <div v-else id="container">
      <MyDisc v-for="disco, i in filtraDischi" :key="i" :details="disco"/> <!-- sostituire il nome della lista, con quello del computed -->
      
    </div> 
    </div>
    
      
  </main>
</template>

<script>

import Load from "@/components/Load.vue";
import MyDisc from "@/components/MyDisc.vue";
import axios from "axios"; // importo axios


export default {
  name: "MyMain",
  components: {
    MyDisc,
    Load
  },
  props: {
    selectedGen: String, // la prop deve ricevere una stringa, che sarebbe la variabile optionSelect che deriva dall'Header
  },

  data() {
    return {
      apiURL: "https://flynn.boolean.careers/exercises/api/array/music", //link per prendere i dati dell'array dall'esterno
      listadischi: [], // array vuoto, in cui viene salvato successivamente l'array esterno
    }
  },
  created() {
    this.getDischi();
  },


  methods: {
    getDischi() {
      axios.get(this.apiURL).then((result) => {this.listadischi = result.data.response;}) //tramite axios, prendiamo il link esterno, e poi lo salviamo nell'array vuoto
    }
  },

  computed: {
    filtraDischi() {
      if(this.selectedGen === "all") {
        return this.listadischi  // se l'option è all, stampa l'intera lista
      }
      return this.listadischi.filter((elem) =>{
        return elem.genre.toLowerCase().includes(this.selectedGen.toLowerCase()) // altrimenti stampa la lista filtrata che contiene l'option
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
        padding-top: 20px;

        #container {
          width: 70%;
          margin: 0 auto;
          display: flex;
          justify-content: space-around;
          flex-wrap: wrap;
        }
    }

</style>
