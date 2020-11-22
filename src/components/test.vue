<template>
   <div class="slideshow-container">
   <div class="slide" v-for="(image, index) in images" :key="index" :class="{'active': index === activeItem, 'not-active': index !== activeItem}">
        <img v-bind:src="image.img" alt="Not found">
   </div>
   <div style="text-align: center">
      <button @click="nextSlide()">Weiter</button>
    </div>
   </div> 
</template>

<script>
export default {
    data(){
        return{
        images: [
            {img: require("../assets/WZ1.jpg")}, 
            {img: require("../assets/WZ2.jpg")}
        ],
        activeItem: 0,
        }
    },
    methods: {
        nextSlide(){
            if(this.activeItem === this.images.length-1){
                this.activeItem = 0;
            }
            else{
                this.activeItem += 1;
            }
        }
    }
}
</script>
<style>
    h1{
        color: red;
    }
    .active{
        display: block;
    }
    .not-active{
        display: none;
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