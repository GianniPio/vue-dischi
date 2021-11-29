<template>
    <div class="disc">
        <div class="immagine">
           <img :src="details.poster" :alt="details.title"> <!--Details == disco -->
        </div>
      <div class="text">
        <p>{{details.title.toUpperCase()}}</p> <!--Per stampare i titoli in maiscuolo--> 
        <span>{{details.author}}</span>
        <span>{{details.year}}</span>
      </div>
      
    </div>
  
</template>

<script>
export default {
  name: "MyDiscs",
  props: { //serve per passare i dati al padre
      details: Object, //details si aspetta un oggetto
  }
 
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

    .disc {
        width: calc(100% / 6);
        height: auto;
        background-color: #2e3a46;
        display: inline-block;
        padding: 15px;
        margin: 5px 5px 20px 5px;
        text-align: center;

        &:hover {
            border: 1px solid white;
            cursor: pointer;
        }

        img {
            width: 100%;
            object-fit: contain;
            
        }

        .text {
            color: white;

            p {
                font-weight: bold;
                padding: 5px 0 10px 0 ;
                width: 100%;
            }

            span {
                display: block;
                color: grey;
                font-size: 13px;
            }
        }
        

        
    }

</style>