<template>
  <div id="selected">
    <form action="">
        <select name="" id="">
            <option value="">Tutti i generi</option>
            <option value="">Rock</option>
            <option value="">Pop</option>
            <option value="">Jazz</option>
            <option value="">Metal</option>
        </select>
        <button>Search</button>
        <button>Reset</button>
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

        button {
            margin: 0 5px 0 15px;
            padding: 5px;
            border: 2px solid cadetblue;
            background-color: cornflowerblue;
            font-size: 15px;
            cursor: pointer;

            &:hover {
                border: 1px solid white;
            }
        }
    }
 }

</style>