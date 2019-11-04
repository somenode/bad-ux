<template>
  <header class="main-head">
    <h1 class="align-center">
      <router-link :to="{ name: 'home' }">Cat World</router-link>
    </h1>
    <nav class="grid-container">
      <ul
        class="vertical menu medium-horizontal grid-x grid-margin-x align-spaced align-middle"
      >
        <li class="cell medium-3">
          <router-link :to="{ name: 'breeds' }">Breeds</router-link>
        </li>
        <li class="cell medium-3">
          <router-link :to="{ name: 'adopt' }">Adopt</router-link>
        </li>
        <li class="cell medium-3">
          <router-link :to="{ name: 'allergies' }">Allergies</router-link>
        </li>
        <li class="cell medium-3">
          <a href="https://www.factretriever.com/cat-facts">Cat Info</a>
        </li>
      </ul>
    </nav>
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
