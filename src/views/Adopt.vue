<template>
  <form id="app" @submit="checkForm" action="https://vuejs.org/" method="post">
    <div class="grid-container">
      <div class="grid-x grid-margin-x">
        <h2 class="cell large-8 large-offset-2 page-header">Adopt</h2>
        <p v-if="errors.length">
          <b>Please correct the following error(s):</b>
        </p>
        <ul>
          <li v-for="error in errors" :key="error">{{ error }}</li>
        </ul>
      </div>
    </div>

    <div class="grid-container">
      <div class="grid-x grid-padding-x">
        <div class="medium-6 cell">
          <label for="name" class="text-left middle">
            Name
            <input id="name" v-model="name" type="text" name="name" />
          </label>
        </div>

        <div class="medium-6 cell">
          <label for="age" class="text-left middle">
            Age
            <input id="age" v-model="age" type="number" name="age" min="0" />
          </label>
        </div>

        <div class="medium-6 cell">
          <label for="tel" class="text-left middle">
            Home phone
            <input id="tel" v-model="tel" type="number" name="tel" min="0" />
          </label>
        </div>

        <div class="medium-6 cell">
          <label for="ctel" class="text-left middle">
            Cell phone
            <input id="ctel" v-model="ctel" type="number" name="ctel" min="0" />
          </label>
        </div>

        <div class="medium-6 cell">
          <label for="email" class="text-left middle">
            Email
            <input id="email" v-model="email" type="email" name="email" />
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
                <input id="state" v-model="city" type="text" name="state" />
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
          <legend class="text-left middle">Housing for your Cat</legend>

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
              <input id="allergyyes" type="checkbox" />
              <label for="allergyyes">Yes</label>
              <input id="allergyno" type="checkbox" />
              <label for="allergyno">No</label>
            </fieldset>

            <div class="medium-6 cell">
              <label for="agreement" class="text-left">
                Is everyone in agreement with the decision to adopt a cat?
              </label>
              <select id="adopt" v-model="adopt" name="adopt">
                <option>Yes</option>
                <option>No</option>
              </select>
            </div>
          </div>
        </fieldset>
        <div class="input-button">
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
      address: null
    }
  },
  methods: {
    checkForm: function(e) {
      if (this.name && this.age) {
        return true
      }

      this.errors = []

      if (!this.name) {
        this.errors.push('Name required.')
      }
      if (!this.age) {
        this.errors.push('Age required.')
      }
      if (!this.address) {
        this.errors.push('Address required.')
      }

      e.preventDefault()
    }
  }
}
</script>
<style scoped>
.address > label {
  padding: 0;
}
</style>
