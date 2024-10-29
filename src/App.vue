
<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled='isplaying'> Play</button>

  <Block v-if="isplaying" :delay ='delay' @end='endGame'/>
  <Results v-if='results' :score='score'/>
</template>

<script >
import Block from './components/Block.vue'
import Results from './components/Results.vue'
export default{
  components: { Block, Results },

  data(){
    return{
      delay :null,
      isplaying :false,
      score :null,
      results : false
    }
  },
  methods:{
     start(){
        this.delay = 2000 + Math.random() * 5000,
        this.isplaying = true
        this.results = false
     },
     endGame(reaction){
        this.score = reaction
        this.isplaying = false;
        this.results= true
     }
  },
  
}
</script>

<style scoped>
h1{
  font-weight: bold;
  color: blue;
  margin: 50px;
}
</style>
