<template>
  <div>
    <NavBar />
    <modal-direction class="style" id="fade-in"></modal-direction>
    <div class="grid-container">
      <div class="grid-x grid-padding-x">
        <p class="cell large-8 large-offset-2">
          Welcome to Cat World.
          <router-link to="/breeds">Browse our cats</router-link>&nbsp; and
          consider
          <router-link to="/adopt-a-cat"
            >&nbsp; applying as an adopter</router-link
          >.
        </p>
        <img class="small-4 cell" v-bind:src="catBelly" />
        <img class="small-4 cell" v-bind:src="catScarf" />
        <img class="small-4 cell" v-bind:src="kittenbigEyes" />
        <img class="small-4 cell" v-bind:src="kittenBasket" />
        <img class="small-4 cell" v-bind:src="kittenGrass" />
        <img class="small-4 cell" v-bind:src="kittenHay" />
        <img class="small-4 cell" v-bind:src="kittengreenEyes" />
        <img class="small-4 cell" v-bind:src="kittencatDog" />
        <img class="small-4 cell" v-bind:src="kittenBabies" />
      </div>
    </div>

    <div class="grid-x grid-padding-x">
      <div class="large-12 cell">
        <video-player :options="videoOptions" class="video-player" />
      </div>
    </div>
    <Footer />
    <footer>
      <cookie-law position="slide-from-top" theme="dark-lime">
        <div slot="message">
          Cat World uses cookies to enhance your experience, for analytics and
          to show you offers tailored to your interests on our site. We may
          share your information with out advertising and analytic partners.
          Find out more by reading our
          <router-link to="policy">Cookies Policy</router-link>&nbsp;which
          contains further information about the cookies and other technologies
          we use and information about how to disable them. By clicking
          “Accept”, you agree to our use of cookies and similar technologies.
        </div>
      </cookie-law>
    </footer>
  </div>
</template>
<script>
import CookieLaw from 'vue-cookie-law'
import NavBar from '@/components/NavBar.vue'
import ModalDirection from '@/components/Modal.vue'
import VideoPlayer from '@/components/VideoPlayer.vue'
import Footer from '@/components/Footer.vue'

export default {
  components: {
    CookieLaw,
    NavBar,
    ModalDirection,
    VideoPlayer,
    Footer
  },
  data: function() {
    return {
      catBelly: require('../assets/cute-cat-belly.jpg'),
      catScarf: require('../assets/cat-scarf.jpg'),
      kittengreenEyes: require('../assets/kitten-greeneyes.jpg'),
      kittenBasket: require('../assets/kittens-basket.jpg'),
      kittenGrass: require('../assets/kittens-grass.jpg'),
      kittenHay: require('../assets/kittens-hay.jpg'),
      kittenbigEyes: require('../assets/bigstock-bigeyes.jpg'),
      kittencatDog: require('../assets/bigstock-cat-dog.jpg'),
      kittenBabies: require('../assets/bigstock-kittens.jpg'),
      videoOptions: {
        autoplay: true,
        controls: true,
        sources: [
          {
            src: require('../assets/meowing.mp4'),
            type: 'video/mp4'
          }
        ]
      }
    }
  }
}
</script>
<style scoped>
p {
  font-size: 1.2em;
}
.video-player {
  z-index: 0;
}

#fade-in {
  -webkit-animation: 3s ease 0s normal forwards 1 fadein;
  -moz-animation: 3s ease 0s normal forwards 1 fadein;
  animation: 3s ease 0s normal forwards 1 fadein;
  z-index: 1000;
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
  position: fixed;
}
.cookies {
  background-color: red;
}

.grid-padding-x > .cell {
  padding-bottom: 0.9375rem;
  padding-top: 0.9375rem;
}

.Cookie.Cookie--slide-from-top.Cookie--dark-lime {
  bottom: 0;
}

a {
  color: #2a33f4;
}
</style>
