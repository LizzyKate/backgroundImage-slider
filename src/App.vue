<template>
 <div class="container">
  <div class="row max-height align-items-center">
   <div class="col-9 col-md-10 mx-auto img-container" ref="show">
    <a class="btn btn-left" v-on:click="btnLeft()"><i class="fas fa-caret-left"></i></a>
    <a class="btn btn-right" v-on:click="btnRight()"><i class="fas fa-caret-right"></i></a>
   </div>
  </div>
 </div>

</template>

<script>

import  './css/main.css'
export default {
  data () {
    return {
      pictures:['contBcg-0.png', 'contBcg-1.png', 'contBcg-2.png', 'contBcg-3.png', 'contBcg-4.png'],
      counter:0
    }
  },
  methods:{
    btnLeft(){
      this.counter--
      if(this.counter < 0){
        this.counter = this.pictures.length - 1;
      }
      this.$refs.show.style.backgroundImage = `url('image/${this.pictures[this.counter]}')`
      console.log("i was clicked")
      console.log(this.$refs.show)
    },
    btnRight(){
      this.counter++
      if(this.counter > this.pictures.length -1){
        this.counter = 0
      }
      this.$refs.show.style.backgroundImage = `url('image/${this.pictures[this.counter]}')`
    }
  }
}
</script>

<style>

</style>
