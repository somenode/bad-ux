<template>
  <div>
    <NavBarLanding />

    <div class="grid-container">
      <div class="grid-x grid-padding-x">
        <div class="small-2 cell"></div>
        <p class="small-8 text-left section-zero">
          This website serves to intentionally highlight terrible user
          experience design. By entering this site, please do not expect a
          pleasant experience. It is riddled with accessibility errors and
          befuddling interactions. To begin, please visit
          <router-link to="/home">this link</router-link>&nbsp;or select the
          button below.
        </p>
        <div class="small-2 cell"></div>

        <div class="small-2 cell"></div>
        <div class="small-8 submit-button">
          <router-link to="/home">
            <button class="button">Find Our Bad UX examples</button>
          </router-link>
        </div>

        <div class="small-2 cell"></div>

        <div class="small-2 cell"></div>
        <h2 class="small-8 text-left section-one separator-left">
          What is Terrible User Experience Design?
        </h2>
        <div class="small-2 cell"></div>

        <div class="small-2 cell"></div>
        <p class="small-8 text-left">
          When we first engage with a digital service, whether it's an app or
          website or building, we notice it's design. The most successful
          companies apply user-centered design principles that are informed by
          user research and testing.
        </p>
        <div class="small-2 cell"></div>

        <div class="small-2 cell"></div>
        <p class="small-8 text-left">
          By terrible UX, we mean the components, interactions, and code that
          are designed without user research and stakeholder collaboration.
          Without research and collaboration, services fail to deliver
          practical, cost-saving services.
        </p>
        <div class="small-2 cell"></div>
        <div class="small-2 cell"></div>
        <p class="small-8 text-left callout primary border-none">
          Please see our
          <a href="https://ux.princeton.edu/learn-ux">Learn UX resources</a>
          that describe how to design excellent digital services.
        </p>
        <div class="small-2 cell"></div>

        <div class="small-2 cell"></div>
        <h2 class="small-8 text-left">Who are Users?</h2>
        <div class="small-2 cell"></div>

        <div class="small-2 cell"></div>
        <p class="small-8 text-left">
          Users are people with diverse backgrounds, perspectives, and life
          experience who engage with your service.
        </p>
        <div class="small-2 cell"></div>

        <div class="small-2 cell"></div>
        <p class="small-8 text-left">
          Great user experience design is also inclusive. In the United States,
          <a
            href="https://www.interactiveaccessibility.com/accessibility-statistics"
            >7.2 million adults have a visual disability</a
          >,
          <a
            href="https://www.interactiveaccessibility.com/accessibility-statistics"
            >7.6 million have a hearing impairment</a
          >, and
          <a
            href="https://www.interactiveaccessibility.com/accessibility-statistics"
            >19.9 million have difficulty lifting or grasping</a
          >
          (which could impact use of a keyboard or mobile phone). UX research,
          testing, and development must include these users and adopt the latest
          technical requirements
          <a
            href="https://www.w3.org/WAI/fundamentals/accessibility-principles/"
            >set by the World Wide Web Consortium (W3C)</a
          >
          and other regulatory bodies.
        </p>

        <div class="small-2 cell"></div>

        <div class="small-2 cell"></div>
        <p class="small-8 text-left callout primary border-none">
          Please see
          <a
            href="https://ux.princeton.edu/learn-ux/blog/discoveries-usability-lab"
            >this post</a
          >
          highlighting discoveries made in our usability lab during user tests.
        </p>
        <div class="small-2 cell"></div>

        <div class="small-2 cell"></div>
        <h2 class="small-8 text-left">Who are Stakeholders?</h2>
        <div class="small-2 cell"></div>

        <div class="small-2 cell"></div>
        <p class="small-8 text-left">
          In addition to users, stakeholders include an organization's
          leadership, administrators, writers, designers, and developers. Each
          group has insight into an organization's high-level goals, daily
          operations, and primary users of the service. Reguarly including
          stakeholders into the design process helps create and recreate digital
          services in efficient ways as priorities change.
        </p>
        <div class="small-2 cell"></div>
        <div class="small-2 cell"></div>
        <p class="small-8 text-left callout primary border-none">
          <a href="https://ux.princeton.edu/learn-ux/certificates"
            >Earn UX certificates</a
          >
          at Princeton University where you learn how to align stakeholder
          priorities with user expectations.
        </p>
        <div class="small-2 cell"></div>
      </div>
    </div>

    <FooterLanding />
  </div>
</template>
<script>
import NavBarLanding from '@/components/NavBarLanding.vue'
import FooterLanding from '@/components/FooterLanding.vue'
export default {
  components: {
    NavBarLanding,
    FooterLanding
  },
  data: function() {
    return {}
  }
}
</script>
<style scoped>
p {
  font-size: 1.2em;
  padding-bottom: 0.8em;
}
.submit-button {
  padding-top: 0.8em;
}
.button {
  background-color: #0e103d;
  padding: 1.3em;
}

.button:hover {
  background-color: white;
  color: #0e103d;
  border-color: #0e103d;
}

.grid-padding-x > .cell {
  padding-bottom: 0.9375rem;
  padding-top: 0.9375rem;
}
.section-zero,
.section-one {
  padding-top: 1.5em;
}
.callout.primary {
  background-color: #f4f9fd;
}
.last-section {
  padding-bottom: 60px;
}
a {
  color: #2a33f4;
}
</style>
