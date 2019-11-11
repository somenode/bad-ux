<template>
  <div v-show="!isHidden" class="modal-mask grid-container fluid">
    <div class="grid-x grid-margin-x">
      <h2 class="large-12 cell">
        🐈 Our Newsletter
        <br />is Purrrr-fect
      </h2>
      <div class="grid-container">
        <div class="grid-x grid-padding-x">
          <div class="medium-6 cell">
            <label for="name" class="text-left middle adopt">
              Name
              <input id="name" v-model="name" type="text" name="name" />
            </label>
          </div>

          <div class="medium-6 cell">
            <label for="email" class="text-left middle adopt">
              Email
              <input id="email" v-model="email" type="email" name="email" />
            </label>
          </div>
          <div class="medium-12 cell yes-subscribe align-right">
            <button @click="isHidden = true">Yes, Subscribe Me!</button>
          </div>
          <div class="medium-12 cell no-subscribe">
            <button @click="isHidden = true">No thanks.</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data: function() {
    return {
      isHidden: false
    }
  }
}
</script>

<style scoped>
.grid-container {
  color: white;
}
label {
  color: white;
  font-size: 1.3em;
}
button,
.yes-subscribe {
  color: white;
  font-size: 1.3em;
  text-align: right;
  cursor: pointer;
}

.no-subscribe {
  color: white;
  font-size: 0.8em;
  text-align: right;
}
.modal-mask {
  padding: 30px;
  transition: opacity 0.3s ease;
  width: auto;
}
</style>
