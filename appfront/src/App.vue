<template>
  <div id="app">
    <Profile></Profile>
    <ProfileEditor></ProfileEditor>
    <router-view>
    </router-view>
  </div>
</template>

<script>
import AboutMeFooter from './components/AboutMeFooter.vue'
import HangOnCard from './components/HangOn.vue'
import AnswerCard from './components/Answer.vue'
import Profile from './components/Profile.vue'
import ProfileEditor from './components/EditProfile.vue'
export default {
  name: 'app',
  components:{
    Profile,
    HangOnCard,
    AnswerCard,
    AboutMeFooter,
    ProfileEditor,
  },
  methods:{
    openProfileForm(){

    }
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
