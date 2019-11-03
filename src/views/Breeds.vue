<template>
  <div class="grid-container">
    <div class="grid-x grid-margin-x">
      <h2 class="cell large-8 large-offset-2 page-header">
        Which Breed of Cat is Right for You?
      </h2>
      <p class="cell large-8 large-offset-2">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua. Arcu ac tortor
        dignissim convallis aenean et. Egestas maecenas pharetra convallis
        posuere morbi leo.
      </p>
    </div>

    <CatType />
  </div>
</template>

<script>
import CatType from '@/components/CatType.vue'

export default {
  components: {
    CatType
  }
}
</script>

<style scoped></style>
