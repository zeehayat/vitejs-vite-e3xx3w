<template>
  <div>
   <h1>Ninja Reaction Timer</h1>
   <button :disabled='isPlaying' @click='start'>Play</button>
   <Block v-if='isPlaying' :delay='delay' @end='endGame' />
   <Results v-if='showResults' :score='score' />
  </div>
  
</template>
<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'
export default{
  name: 'App',

  components:{
    Block,Results
  },
  data(){
    return {
      isPlaying:false,
      delay: null,
      score:null,
      showResults:false
    }
  },
  methods:{
    start(){
      this.delay=2000 + Math.random() * 5000
      this.showResults=false
      this.isPlaying=true
      
    },
    endGame(reactionTime){
      this.score=reactionTime
      this.isPlaying=false
      this.showResults=true
    }
  }
}
</script>
<style scoped>

</style>
