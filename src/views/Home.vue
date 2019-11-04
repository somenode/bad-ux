<template>
  <div class="grid-container">
    <div class="grid-x grid-margin-x">
      <h2 class="cell large-8 large-offset-2 page-header">Home</h2>
      <p class="cell large-8 large-offset-2">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua. Arcu ac tortor
        dignissim convallis aenean et. Egestas maecenas pharetra convallis
        posuere morbi leo.
      </p>
    </div>
  </div>
  <!-- <div>
    <div>
      <div v-if="isOpen">
        <h1>Modal heading</h1>
        <p>This my first modal using vue.js</p>
      </div>
      <button @click="isOpen = !isOpen">Open modal</button>
    </div>
  </div>-->
</template>

<script>
export default {
  data: function() {
    return {
      isOpen: false
    }
  },
  methods: {
    callFunction: function() {
      var v = this
      setTimeout(function() {
        v.message =
          'Cat World uses cookies to enhance your experience, for analytics and to show you offers tailored to your interests on our site. We may share your information with out advertising and analytic partners. Find out more by reading our Cookies Policy which contains further information about the cookies and other technologies  we use and information about how to disable them. By clicking “Accept”, you agree to our use of cookies and similar technologies.'
      }, 2000)
    }
  },
  mounted() {
    this.callFunction()
  }
}
</script>
<style scoped>
.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: table;
  transition: opacity 0.3s ease;
}

.modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}

.modal-container {
  width: 300px;
  margin: 0px auto;
  padding: 20px 30px;
  background-color: #fff;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
  transition: all 0.3s ease;
  font-family: Helvetica, Arial, sans-serif;
}

.modal-header h3 {
  margin-top: 0;
  color: #42b983;
}

.modal-body {
  margin: 20px 0;
}

.modal-default-button {
  float: right;
}

/*
 * The following styles are auto-applied to elements with
 * transition="modal" when their visibility is toggled
 * by Vue.js.
 *
 * You can easily play with the modal transition by editing
 * these styles.
 */

.modal-enter {
  opacity: 0;
}

.modal-leave-active {
  opacity: 0;
}

.modal-enter .modal-container,
.modal-leave-active .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
</style>
