<template>
  <div id="app">
    <Profile ref="profile" v-on:editProfile="openProfileForm"></Profile>
    <ProfileEditor ref="editor"></ProfileEditor>
    <router-view>
    </router-view>
    <AnswerCard></AnswerCard>
    <HangOnCard></HangOnCard>
    <Footer></Footer>
  </div>
</template>

<script>
import Footer from './components/AboutMeFooter.vue'
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
    Footer,
    ProfileEditor,
  },
  methods:{
    openProfileForm(edit){
      if(edit){
        this.$refs.editor.show(edit);
      }
    },
    setProfile: function (data) {
      if(data.signed){
        this.$refs.profile.setProfile(data)
      }else {
        this.$refs.editor.show(false);
      }
    },
    initProfile(){
      const outer = this;
      this.$axios.get('/getHome')
        .then(function (response) {
//          const data = JSON.parse(response);
          outer.setProfile(response);
        })
    }
  },
  created:function () {
    this.initProfile()
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
