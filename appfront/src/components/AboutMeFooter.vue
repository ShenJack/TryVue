<template>
  <footer id="myFooter" class="footer">
    <div class="container">
      <div class="content has-text-centered">
        <p>
          如有任何疑问，请联系作者微信<a href="https://jgthms.com"></a>.
        </p>
        <button id="button" @click.native="showModal" class="button is-primary modal-button" data-target="modal">
          二维码
        </button>


      </div>
      <div id="modal" class="modal" :class="[isShow]">
        <div class="modal-background"></div>
        <div class="modal-content">
          <p class="image is-4by3">
            <img src="https://bulma.io/images/placeholders/1280x960.png" alt="">
          </p>
        </div>
        <button @click.native="hideModal" class="modal-close is-large" aria-label="close"></button>
      </div>
    </div>

  </footer>
</template>

<script type="text/javascript">
  import Vue from 'Vue'

  export default {
    name: 'AboutMeFooter'
  }

  var footer = new Vue({
    name: 'myFooter',
    data: {
      isShow: ''
    },
    methods: {
      showModal: function (event) {
        alert('afowi');
        this.isShow = 'is-alive';
      },
      hideModal: function (event) {
        this.isShow = ''
      }
    }
  });
</script>
