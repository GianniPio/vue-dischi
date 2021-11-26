<template>
  <div id="header">
      <!-- div si riferimento per l'icona -->
    <div id="icon">
        <i class="fab fa-spotify"></i> <!--Icona di spotify-->
    </div>
  </div>
</template>

<script>
export default {
  name: "MyHeader",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

    #header {
        background-color: #2e3a46;

        #icon {
            color: #1ed760;
            font-size: 40px;
            padding: 10px 20px;
            
            i {
                cursor: pointer;
            }
        }
    }

</style>
