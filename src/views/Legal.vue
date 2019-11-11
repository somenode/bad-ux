<template>
  <div>
    <NavBar />
    <div class="grid-container">
      <div class="grid-x grid-padding-x">
        <h2 class="cell medium-8 large-offset-2 page-header">Cookie Policy</h2>
        <p class="cell medium-8 large-offset-2">
          🍪 We don't sell your information to any advertisers.
        </p>
        <p class="cell medium-8 large-offset-2">
          🍪 This website is purely for educational purposes that highlight
          terrible user experience examples. It is intentionally inaccessible by
          design.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue'
export default {
  components: {
    NavBar
  }
}
</script>

<style scoped>
h2 {
  padding-bottom: 50px;
}
p {
  text-align: left;
  font-size: 2em;
  padding-bottom: 20px;
}
</style>
