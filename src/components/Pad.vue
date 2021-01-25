<template>
  <button class="pad" :class="hit ? 'down':null" @click="push" >
    {{pad.label}} - ({{pad.trigger}})
  </button>
</template>
<script>
export default {
  props:{
    pad:{
      type:Object,
      default:()=>{}
    }
  },
  data(){
    return{
      hit:false,
      audio:''
    }
  },
  mounted(){

    this.audio=new Audio(`/sounds/${this.pad.sound}`);
    this.audio.preload=true
  },
  methods:{
    push(val){        
        this.audio.pause();
        this.audio.currentTime = 0;
        this.audio.play()

    },
   
  }
}
</script>
<style lang="scss">
.pad{
  width:100%;
  aspect-ratio:1 / 1;
  border:none;
  text-transform:uppercase;
  font-weight:bold;
  color:white;
  background-image:linear-gradient(#F00,#F6F);
  border-radius:5px;
  display:flex;
  justify-content:center;
  align-items:center;
  cursor:pointer;
  transition:all .02s ease-in-out;
  &.down{
  background-image:linear-gradient(#FF0,#06F);

  }
  &:hover{
    box-shadow: 0px -4px 10px #F88;
    transform:translateY(2px);
  }
  &:focus{
    outline:none;
  }
}
</style>
