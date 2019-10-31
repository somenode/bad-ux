<template>
  <header class="subnav-hero-section">
    <h1 class="subnav-hero-headline">Cat World</h1>
    <nav class="subnav-hero-subnav">
      <ul>
        <li>
          <router-link :to="{ name: 'home' }">Home</router-link>
        </li>
        <li>
          <router-link :to="{ name: 'breeds' }">Breeds</router-link>
        </li>
        <li>
          <router-link :to="{ name: 'adopt' }">Adopt A Cat</router-link>
        </li>
        <li>
          <router-link :to="{ name: 'allergies' }">Allergies</router-link>
        </li>
        <li>
          <router-link :to="{ name: 'info' }">Cat Info</router-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped></style>
