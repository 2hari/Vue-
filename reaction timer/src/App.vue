<template>
  <button @click="start" :disabled="isPlaying">play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <Results v-if="showResults" :score="score"/>
</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'
export default {
  name:'Reaction time app',
  components:{Block,Results},
  data(){
    return {
      isPlaying:false,
      delay:null,
      score:null,
      showResults:false
    }
  },
  methods:{
    start(){
      this.delay = 500 + Math.random()*2000
      this.isPlaying = true
      this.showResults = false
     },
     endGame(reactionTime){
       this.score = reactionTime
       this.isPlaying = false
       this.showResults = true
     }
  }
}
</script>


<style>

</style>
