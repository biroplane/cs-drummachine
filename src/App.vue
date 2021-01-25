<template>
  <div id="app">
  <div class="container">
  <pad v-for="(pad,p) in pads" :key="p" :pad="pad" />
  
  </div>
  </div>
</template>

<script>
import Pad from "@/components/Pad";

export default {
  name: "App",
  data(){
    return {
      pads:[
        {trigger:"1",sound:"AverageKick.wav",label:"Kick"},
        {trigger:"2",sound:"FunkHat.wav",label:"Hat"},
        {trigger:"3",sound:"SmackSnare.wav",label:"Snare"},
        {trigger:"4",sound:"AverageKick.wav",label:"Kick"},
        {trigger:"q",sound:"FunkHat.wav",label:"Kick"},
        {trigger:"w",sound:"SmackSnare.wav",label:"Kick"},
        {trigger:"e",sound:"AverageKick.wav",label:"Kick"},
        {trigger:"r",sound:"FunkHat.wav",label:"Kick"},
        {trigger:"a",sound:"SmackSnare.wav",label:"Kick"},
        {trigger:"s",sound:"AverageKick.wav",label:"Kick"},
        {trigger:"d",sound:"FunkHat.wav",label:"Kick"},
        {trigger:"f",sound:"SmackSnare.wav",label:"Kick"},
        {trigger:"z",sound:"AverageKick.wav",label:"Kick"},
        {trigger:"x",sound:"FunkHat.wav",label:"Kick"},
        {trigger:"c",sound:"SmackSnare.wav",label:"Kick"},
        {trigger:"v",sound:"SmackSnare.wav",label:"Kick"},
      ]
    }
  },
  components:{
    Pad
  },
  created(){
    window.addEventListener('keydown',(e)=>{
      console.log("Keydown",e)
    })
  }
  
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  color: #2c3e50;
  margin-top: 60px;
  display:flex;
  width:100vw;
  height:100vh;
  justify-content:center;
  align-items:center;

}
.container{
  display:grid;
  grid-template-columns: repeat(4, minmax(100px, 1fr));
  column-gap:1rem;
  row-gap:1rem;
  max-width:500px;
}
</style>
