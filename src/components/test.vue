<template>
   <div class="slideshow-container">
   <div class="slides" v-for="img in images" v-bind:key="img" ref="slide">
        <img v-bind:src="img" alt="Not found">
   </div>
   <div style="text-align: center">
      <span class="dot" @click="nextSlide(0)"></span>
      <span class="dot" @click="nextSlide(1)"></span>
    </div>
   </div> 
</template>

<script>
export default {
    data(){
        return{
        images: [
            require("../assets/WZ1.jpg"), 
            require("../assets/WZ2.jpg")
        ]
        }
    },
    methods: {
        nextSlide(x){
            console.log(x)
            // Hier sollte eigentlich wie in der Doku beschrieben, ein Array ausgegeben... Wird aber nur das letzte
            // Element ausgegeben. GabeN pls fix
            console.log(this.$refs['slide'])
            this.$refs['slide'].style.backgroundColor = 'red';
        }
    }
}
</script>
<style>
    h1{
        color: red;
    }
    .dot {
  cursor: pointer;
  height: 15px;
  width: 15px;
  margin: 0 2px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.6s ease;
}
</style>