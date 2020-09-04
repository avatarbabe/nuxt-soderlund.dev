<template>
  <footer class="footer -mx-4 md:mx-0">
    <div class="container mx-auto pb-6 flex justify-center">
      <a href="mailto:marcus_soderlund@yahoo.se" target="email">
        <img alt="mail" src="images/uploads/mail.svg" />
      </a>
      <a href="https://github.com/avatarbabe" target="_blank">
        <img alt="github" src="images/uploads/github.svg" />
      </a>
      <a class="ml-4" href="https://www.instagram.com/soderlund_marcus" target="_blank">
        <img alt="instagram" src="images/uploads/instagram.svg" />
      </a>
      <a class="ml-4" href="https://www.linkedin.com/in/soderlundmarcus" target="_blank">
        <img alt="linkedin" src="images/uploads/linkedin.svg" />
      </a>
    </div>
  </footer>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';

@Component
export default class Footer extends Vue {}
</script>

<style lang="scss">
.footer {
  background-color: $bluise;
}
</style>
