<template>
  <div>
    <modal-direction class="style" id="fade-in"></modal-direction>
    <div class="grid-container">
      <div class="grid-x grid-margin-x">
        <h2 class="cell large-8 large-offset-2 page-header">Adopt</h2>
        <p class="cell large-8 large-offset-2">
          Thank you for considering to adopt one of our cats!
          <br />Please fill out the form below and we'll be in touch soon.
        </p>
        <AdoptForm />
      </div>
    </div>
  </div>
</template>
<script>
import ModalDirection from '@/components/Modal.vue'
import AdoptForm from '@/components/AdoptForm.vue'
// import ModalSubscribe from '@/components/ModalSubscribe.vue'

export default {
  components: {
    ModalDirection,
    AdoptForm
  },
  data: function() {
    return {
      errors: [],
      name: null,
      age: null,
      address: null,
      city: null,
      state: null,
      zip: null,
      tel: null,
      ctel: null,
      email: null,
      vet: null,
      adults: null,
      children: null,
      home: null,
      companionship: null,
      caring: null,
      stress: null,
      rodent: null,
      affection: null,
      selected: ''
    }
  },
  methods: {
    checkForm: function(e) {
      this.errors = []

      if (!this.name || !this.email || !this.age) {
        this.errors.push('😱 This is required.')
      }

      if (this.age < 18 || this.age > 100) {
        this.errors.push('🙃 Sorry, you are ineligible.')
      }

      if (!this.validEmail(this.email)) {
        this.errors.push('😱 Valid email required.')
      }

      if (!this.address || !this.city || !this.vet) {
        this.errors.push('😱 Please fill this field out.')
      }

      if (!this.state || !this.zip) {
        this.errors.push('😱 Field response missing.')
      }
      if (!this.children || !this.adults || !this.home) {
        this.errors.push('😱 Please correct this information.')
      }

      if (
        !this.companionship &&
        !this.caring &&
        !this.stress &&
        !this.rodent &&
        !this.affection
      ) {
        this.errors.push('👉 Please select one')
      }

      if (
        (this.companionship && this.caring) ||
        (this.companionship && this.stress) ||
        (this.companionship && this.rodent) ||
        (this.companionship && this.affection) ||
        (this.caring && this.stress) ||
        (this.caring && this.rodent) ||
        (this.caring && this.affection) ||
        (this.stress && this.rodent) ||
        (this.stress && this.affection) ||
        (this.affection && this.rodent)
      ) {
        this.errors.push('👉 Please select one')
      }
      if (!this.errors.length) {
        return true
      }

      e.preventDefault()
    },

    validEmail: function(email) {
      var re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
      return re.test(email)
    }
  }
}
</script>
<style scoped>
#fade-in {
  -webkit-animation: 5s ease 0s normal forwards 1 fadein;
  animation: 5s ease 0s normal forwards 1 fadein;
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

p {
  font-size: 1.2em;
}
.adopt {
  font-size: 1.1em;
}
.box {
  border: 1px solid rgba(255, 255, 255, 0.5);
  padding: 8px 20px;
  line-height: 1.2em;
  opacity: 0;
  color: white;
  width: 100%;
  height: 500px;
  margin: 0 auto;
  margin-top: 30px;
  transform: translateZ(0);
  perspective: 1000px;
  backface-visibility: hidden;
  background: rgba(255, 255, 255, 0.1);
  transition: 0.3s all cubic-bezier(0.39, 0.575, 0.565, 1);
}
.newsletter {
  color: white;
  font-size: 1.2em;
  font-weight: bold;
}

.address > label {
  padding: 0;
}
li {
  list-style-type: none;
}
input {
  margin-bottom: 0;
}
.box-data {
  text-align: left;
}
</style>
