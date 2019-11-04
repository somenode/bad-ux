<template>
  <form id="app" @submit="checkForm" action="./thank-you">
    <div class="grid-container">
      <div class="grid-x grid-margin-x">
        <h2 class="cell large-8 large-offset-2 page-header">Adopt</h2>
        <p class="cell large-8 large-offset-2">
          Thank you for considering to adopt one of our cats!
          <br />Please fill out the form below and we'll be in touch soon.
        </p>
        <p v-if="errors.length" class="medium-12 cell">
          <b>Please correct the following error(s):</b>
        </p>

        <ul class="medium-12 cell">
          <li v-for="error in errors" :key="error.length">{{ error }}</li>
        </ul>
      </div>
    </div>

    <div class="grid-container">
      <div class="grid-x grid-padding-x">
        <div class="medium-6 cell">
          <label for="name" class="text-left middle">
            Name*
            <input id="name" v-model="name" type="text" name="name" />
            <span class="help-text"
              >Please fill out your first and last name.</span
            >
          </label>
        </div>

        <div class="medium-6 cell">
          <label for="age" class="text-left middle">
            Age*
            <input id="age" v-model="age" type="number" name="age" min="0" />
            <span class="help-text">Please fill out your age.</span>
          </label>
        </div>

        <div class="medium-6 cell">
          <label for="tel" class="text-left middle">
            Home phone
            <input id="tel" v-model="tel" type="number" name="tel" min="0" />
            <span class="help-text"
              >Please fill out your home phone number.</span
            >
          </label>
        </div>

        <div class="medium-6 cell">
          <label for="ctel" class="text-left middle">
            Cell phone
            <input id="ctel" v-model="ctel" type="number" name="ctel" min="0" />
            <span class="help-text"
              >Please fill out your cell phone number.</span
            >
          </label>
        </div>

        <div class="medium-6 cell">
          <label for="email" class="text-left middle">
            Email*
            <input id="email" v-model="email" type="email" name="email" />
            <span class="help-text">Please fill out your email.</span>
          </label>
        </div>

        <div class="medium-6 cell">
          <label for="ver" class="text-left middle">
            Your veterinarian
            <input id="ver" v-model="vet" type="text" name="vet" />
          </label>
        </div>

        <fieldset class="medium-12 cell address fieldset">
          <legend class="text-left middle">Mailing Address</legend>
          <label for="address" class="text-left middle">
            Address
            <input id="address" v-model="address" type="text" name="address" />
          </label>
          <div class="grid-x grid-padding-x">
            <div class="medium-6 cell">
              <label for="city" class="text-left middle">
                City
                <input id="city" v-model="city" type="text" name="city" />
              </label>
            </div>
            <div class="medium-6 cell">
              <label for="State" class="text-left middle">
                State
                <input id="state" v-model="state" type="text" name="state" />
              </label>
            </div>
            <div class="medium-6 cell">
              <label for="zip" class="text-left middle">
                Zip
                <input id="zip" v-model="zip" type="number" name="zip" />
              </label>
            </div>
          </div>
        </fieldset>

        <fieldset class="medium-12 cell address fieldset">
          <legend class="text-left middle">Housing for Your Cat</legend>

          <div class="grid-x grid-padding-x">
            <div class="medium-6 cell">
              <label for="adults" class="text-left middle">
                Number of adults in household
                <input
                  id="adults"
                  v-model="adults"
                  type="number"
                  name="adults"
                  min="1"
                />
              </label>
            </div>
            <div class="medium-6 cell">
              <label for="children" class="text-left middle">
                Number of children in the household (under 18)
                <input
                  id="children"
                  v-model="children"
                  type="number"
                  name="children"
                  min="1"
                />
              </label>
            </div>
            <div class="medium-6 cell">
              <label for="home" class="text-left"
                >What type of home do you live in?</label
              >
              <select id="home" v-model="home" name="home">
                <option>Single Family</option>
                <option>Town Home</option>
                <option>Apartment</option>
                <option>Studio</option>
                <option>Farm</option>
                <option>Condo</option>
                <option>Other</option>
              </select>
            </div>

            <fieldset class="medium-6 cell">
              <legend>Is anyone in the family allergic to cats?</legend>
              <input id="allergyyes" type="checkbox" v-model="checkedyes" />
              <label for="allergyyes">Yes</label>
              <input id="allergyno" type="checkbox" v-model="checkedno" />
              <label for="allergyno">No</label>
            </fieldset>

            <div class="medium-6 cell">
              <label for="adopt" class="text-left">
                Is everyone in agreement with the decision to adopt a cat?
              </label>
              <select id="adopt" v-model="selected" name="adopt">
                <option id="adoptyes">Yes</option>
                <option id="adoptno">No</option>
              </select>
            </div>
          </div>
        </fieldset>
      </div>
    </div>
    <div class="grid-container">
      <div class="grid-x grid-padding-x align-right">
        <div class="small">
          <input type="submit" class="button" value="Submit" />
        </div>
      </div>
    </div>
  </form>
</template>
<script>
export default {
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
      checkedyes: null,
      checkedno: null,
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
      if (!this.checkedyes && !this.checkedno) {
        this.errors.push('👉 Please select one.')
      }
      if (this.checkedyes && this.checkedno) {
        this.errors.push('👉 Please select one.')
      }

      if (this.checkedyes && this.selected == 'Yes') {
        this.errors.push('🤔 Are you sure you should adopt?')
      }

      if (this.checkedyes && this.selected == 'No') {
        this.errors.push('😮 Why?')
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
.address > label {
  padding: 0;
}
li {
  list-style-type: none;
}
input {
  margin-bottom: 0;
}
</style>
