<template>
<div class='result'>
{{score}}
</div>
</template>

<script>
export default{
  props:['score']
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