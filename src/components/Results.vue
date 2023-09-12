<template>
<div class='result'>
{{score}} || {{this.rank}}
</div>
</template>

<script>
export default{
  props:['score'],
  data(){
    return {
      rank:null
    }
  },
  mounted(){
    if(this.score<250){
      this.rank='You are a Ninja'
    }
    else if (this.score<500){
      this.rank='Quick Reflexes'
    }
    else {
      this.rank='Slow Coach'
    }
  }
}
</script>
<style>
.result{
  display:block;
  background:yellow;
  color:red;
  padding:10px;
  margin:10px;
}
</style>