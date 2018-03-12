<template>
  <div id="app">
    <router-view>

    </router-view>
    <AnswerCard></AnswerCard>
    <HangOnCard></HangOnCard>
    <AboutMeFooter></AboutMeFooter>
  </div>
</template>

<script>
import AboutMeFooter from './components/AboutMeFooter.vue'
import AnswerCard from './components/Answer.vue'
import HangOnCard from './components/HangOn'
export default {
  name: 'app',
  components:{
    HangOnCard,
    AnswerCard,
    AboutMeFooter,
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
