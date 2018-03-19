<template>
  <div id="app">
    <Profile ref="myProfile" v-on:editProfile="openProfileForm"></Profile>
    <ProfileEditor ref="editor"></ProfileEditor>
    <router-view>
    </router-view>
    <AnswerCard v-show="doAnswer"></AnswerCard>
    <HangOnCard v-show="doHangOn"></HangOnCard>
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
    components: {
      Profile,
      HangOnCard,
      AnswerCard,
      Footer,
      ProfileEditor,
    },
    data(){
      return{
        doAnswer:false,
        doHangOn:false,
      }
    },
    methods: {
      openProfileForm(edit) {
        if (edit) {
          this.$refs.editor.show(edit);
        }
      },
      setProfile: function (data) {
        console.log(data.signed);
        if (data.signed) {
          this.$refs.myProfile.setProfile(data)
        } else {
          this.$refs.editor.show(false);
        }
      },
      setComponents: function (data) {
        this.doAnswer = data.doAnswer;
        this.doHangOn = data.doHangOn;
      },
      initProfile() {
        const outer = this;
        this.$axios.get('/getHome')
          .then(function (response) {
            const data = response.data;
            outer.setProfile(data);
            outer.setComponents(data);
          })
      }
    },
    created: function () {
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
