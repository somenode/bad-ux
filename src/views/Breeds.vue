<template>
  <div>
    <modal-direction class="style" id="fade-in"></modal-direction>
    <div class="grid-container">
      <div class="grid-x grid-margin-x">
        <h2 class="cell large-8 large-offset-2 page-header">
          Which Breed of Cat is Right for You?
        </h2>
        <p class="cell large-8 large-offset-2">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua. Arcu ac
          tortor dignissim convallis aenean et. Egestas maecenas pharetra
          convallis posuere morbi leo.
        </p>
      </div>

      <CatType />
    </div>
  </div>
</template>

<script>
import CatType from '@/components/CatType.vue'
import ModalDirection from '@/components/Modal.vue'

export default {
  components: {
    CatType,
    ModalDirection
  },
  data() {
    return {
      active: false
    }
  }
}
</script>

<style scoped>
#fade-in {
  -webkit-animation: 3s ease 0s normal forwards 1 fadein;
  animation: 3s ease 0s normal forwards 1 fadein;
}

@keyframes fadein {
  0% {
    opacity: 0;
  }
  66% {
    opacity: 0;
  }
  100% {
    opacity: 0.9;
  }
}

@-webkit-keyframes fadein {
  0% {
    opacity: 0;
  }
  66% {
    opacity: 0;
  }
  100% {
    opacity: 0.9;
  }
}

.style {
  top: 0px;
  margin: 0px;
  width: 100%;
  height: 100%;
  background: #310d20;
  animation-delay: 5s;
  -webkit-animation-delay: 5s;
  animation: fadeIn ease 2s;
  -moz-animation-delay: 5s;
  animation: fadeIn ease 2s;
  -webkit-animation: 3s ease 0s normal forwards 1 fadein;
  -moz-animation: 3s ease 0s normal forwards 1 fadein;
  position: fixed;
}
p {
  font-size: 1.2em;
}
</style>
