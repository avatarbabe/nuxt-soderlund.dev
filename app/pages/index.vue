<template>
  <section class="home">
    <div
      class="container py-2 md:py-36 mx-auto flex flex-wrap flex-col-reverse md:flex-row items-center"
    >
      <div class="flex flex-col w-full md:w-1/2 justify-center lg:items-start overflow-y-hidden">
        <div v-html="$md.render(welcomeText)" class="home__welcome markdown" />

        <div class="mb-12 xl:mb-0">
          <h4 v-if="isSignedUp">Thank you - we'll be in touch shortly.</h4>

          <button
            class="flex flex-shrink-0 bg-blue-500 hover:bg-blue-700 border-blue-500 hover:border-blue-700 text-sm font-medium border-4 text-white py-1 px-2 rounded"
            type="submit"
          >
            Contact me
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="24"
              height="24"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
              class="feather feather-arrow-right ml-2"
            >
              <line x1="5" y1="12" x2="19" y2="12"></line>
              <polyline points="12 5 19 12 12 19"></polyline>
            </svg>
          </button>
        </div>
      </div>
      <div class="flex flex-col w-full md:w-1/2">
        <img alt="Hero" class="" src="/images/uploads/marcus.png" />
      </div>
    </div>
    <img alt="wave" class="" src="/images/uploads/wave-1.svg" />
    <div class="container flex flex-col relative">
      <div class="contact__container w-full text-center">
        <h3 class="text-5xl font-bold">Contact me</h3>
        <p class="text-xl lg:mb-24 mb-12">
          Feel free to contact me if you have any questions, inquiries or just want to chat :)
        </p>
        <div
          class="container mx-auto pb-6 flex justify-center grid grid-cols-2 xl:grid-cols-4 w-1/2 md:w-1/6 xl:w-1/4"
        >
          <a href="mailto:marcus_soderlund@yahoo.se" target="email">
            <img alt="mail" src="images/uploads/mail-black.svg" />
          </a>
          <a href="https://github.com/avatarbabe" target="_blank">
            <img alt="github" src="images/uploads/github-black.svg" />
          </a>
          <a href="https://www.instagram.com/soderlund_marcus" target="_blank">
            <img alt="instagram" src="images/uploads/instagram-black.svg" />
          </a>
          <a href="https://www.linkedin.com/in/soderlundmarcus" target="_blank">
            <img alt="linkedin" src="images/uploads/linkedin-black.svg" />
          </a>
        </div>
      </div>
      <div class="flex items-end">
        <div class="-mr-12 hidden xl:block">
          <img alt="ground" class="" src="/images/uploads/ground.svg" />
          <div class="h-24"></div>
        </div>
        <img
          alt="contact-me"
          class="hidden md:block ml-auto"
          src="/images/uploads/contact-me.svg"
        />
      </div>
    </div>
    <img
      alt="contact-me"
      class="md:hidden -mt-24 ml-auto"
      src="/images/uploads/contact-me-small.svg"
    />
  </section>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import settings from '@/content/settings/general.json';

@Component({
  // Called to know which transition to apply
  transition() {
    return 'slide-left';
  },
})
export default class Home extends Vue {
  welcomeText = settings.welcomeText;

  get posts(): Post[] {
    return this.$store.state.posts;
  }

  isSignedUp = false;

  encode(data): string {
    return Object.keys(data)
      .map((key) => `${encodeURIComponent(key)}=${encodeURIComponent(data[key])}`)
      .join('&');
  }
}
</script>
<style lang="scss" scoped>
.contact__container {
  top: -5rem;

  @screen md {
    position: absolute;
    top: 2rem;
  }
  @screen lg {
    top: 6rem;
  }
  .container {
    justify-items: center;
  }
}
</style>
