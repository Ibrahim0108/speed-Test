<template>
  <p> Reaction Time {{score}} ms</p>
  <h2>{{rank}}</h2>
</template>

<script>
export default {
   props:['score'],
   data(){
    return{
        rank :null
    }
   },
   mounted(){
    if (this.score <250){
        this.rank ='god speed '
    }else if (this.score < 400){
        this.rank ='fast refex'
    }else{
        this.rank ='slow man'
    }
   }
}
</script>

<style>

</style>