<template>
  <div>
    <NavBar />

    <div class="grid-container">
      <div class="grid-x grid-margin-x">
        <h2 class="cell large-8 large-offset-2 page-header">Which Breed of Cat is Right for You?</h2>
        <p class="cell large-8 large-offset-2">
          As of 2019, The
          <a href="https://tica.org/">International Cat Association</a>
          recognizes 71 standardized breeds, the
          <a
            href="http://www.cfa.org/"
          >Cat Fanciers' Association</a> recognizes
          44, and the
          <a
            href="http://fifeweb.org/index.php"
          >Federation International Feline</a>
          recognizes 43. There are so many breeds to choose from.
        </p>
      </div>

      <CatType />
    </div>
    <Footer />
  </div>
</template>

<script>
import CatType from '@/components/CatType.vue'
import NavBar from '@/components/NavBar.vue'
import Footer from '@/components/Footer.vue'

export default {
  components: {
    CatType,
    NavBar,
    Footer
  },
  data() {
    return {
      active: false
    }
  }
}
</script>

<style scoped>
p {
  font-size: 1.2em;
}
a {
  color: #2a33f4;
}
</style>
