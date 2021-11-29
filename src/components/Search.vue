<template>
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
</template>

<script>
export default {
  name: "Search",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

 #selected {
     width: 100%;
    
    form {
        text-align: center;
        padding: 20px 0;

        select {
            padding: 5px;
            border: 2px solid cadetblue;
            font-size: 15px;
        }
    }
 }

</style>