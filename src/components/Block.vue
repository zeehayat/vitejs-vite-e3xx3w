<template>
  <div class="block" v-if='showBlock' @click='stopTimer'>Click Me<br>
  
  
  </div>
  
</template>
<script>
export default {
  props: ['delay'],
  data(){
    return {
      showBlock:false,
      timer:null,
      reactionTime:0
    }
  },
  mounted(){
    setTimeout(()=>{
      this.showBlock=true
      this.startTimer()
    },this.delay)
  },
  methods:{
    startTimer(){
      this.timer=setInterval(()=>{
        this.reactionTime+=10
      },10)
    },
    stopTimer(){
      clearInterval(this.timer)
      this.$emit('end',this.reactionTime)
    }
  }
}

</script>

<style>
.block {
  width: 200px;
  height: 200px;
  background-color: blue;
  color: white;
  padding: 100px;
  margin: 48px;
}
</style>
