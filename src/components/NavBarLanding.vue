<template>
  <header class="main-head">
    <h1 class="align-center">
      <router-link :to="{ name: 'landing' }"
        >Welcome to Bad User Experience</router-link
      >
    </h1>
    <nav class="grid-container"></nav>
  </header>
</template>

<script>
export default {}
</script>

<style scoped>
h1 a {
  font-size: 1.6em;
  color: #ffffff;
  line-height: 2.2;
  text-transform: uppercase;
  font-weight: 700;
}
.main-head {
  padding: 40px 0px;
  background-color: #0e103d;
}
.title-bar {
  background-color: #0e103d;
}

.menu a {
  color: #ffffff;
  text-transform: uppercase;
  font-size: 1.3em;
}
</style>
