<template>
  <header>
      <!-- div si riferimento per l'icona -->
    <div id="icon">
        <i class="fab fa-spotify"></i> <!--Icona di spotify-->
    </div>

    <div id="selected">
    <form action="">
        <select name="genre" id="" @change="$emit('changeSelect', $event)"> <!-- al cambio della selezione, il padre tramite changeSelect, richiama un metodo e passa il valore come evento -->
            <option :value="'all'">Tutti i generi</option>
            <option :value="'rock'">Rock</option>
            <option :value="'pop'">Pop</option>
            <option :value="'jazz'">Jazz</option>
            <option :value="'metal'">Metal</option>
        </select>
    </form>
  </div>
  </header>
</template>

<script>
export default {
  name: "MyHeader",

};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

    header {
      background-color: #2e3a46;
      display: flex;
      justify-content: space-between;

        #icon {
        color: #1ed760;
        font-size: 40px;
        padding: 10px 20px;
        
        i {
          cursor: pointer;
        }
      }

      #selected {
      width: 100%;
      padding: 25% 0;
     
    
      form {
        text-align: right;
        margin-right: 25px;

      select {
        padding: 5px;
        border: 2px solid cadetblue;
        font-size: 15px;
      }
    }
 }


    }

</style>
