<template>
  <footer>
    <h3 class="align-center">About This Site</h3>
    <nav class="grid-container">
      <div class="grid-x grid-padding-x">
        <p class="small-6 cell text-left">
          This website serves to intentionally highlight terrible user
          experience design. By using this site, please do not expect a pleasant
          experience. It is riddled with accessibility errors and befuddling
          interactions.
        </p>
        <p class="small-6 cell text-left">
          For best practices in user experience design, please visit
          <a href="https://ux.princeton.edu">ux.princeton.edu</a> or contact the
          <a href="mailto:ux@princeton.edu?subject=Bad%20UX%20Design%20Site"
            >User Experience Office</a
          >
          at Princeton University.
        </p>
      </div>
    </nav>
  </footer>
</template>

<script>
export default {}
</script>

<style scoped>
h3 {
  color: #ffffff;
  line-height: 2.2;
  text-transform: uppercase;
  font-weight: 700;
}
footer {
  padding: 40px 0px;
  background: #0e103d;
  bottom: 0;
  margin-top: 50px;
}
.title-bar {
  background-color: #0e103d;
}

.menu a {
  color: #ffffff;
  text-transform: uppercase;
  font-size: 1.3em;
}
p {
  color: #ffffff;
}
</style>
