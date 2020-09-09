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
            class="flex flex-shrink-0 bg-primary hover:bg-blue-700 border-blue-800 hover:border-blue-700 text-sm font-medium border-4 text-white py-1 px-2 rounded"
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
    <img alt="wave" class="wave-top w-full" src="/images/uploads/wave-1.svg" />
    <div class="bg-primary w-full">
      <div class="about-container">
        <div>
          <h2 class="text-primary text-5xl">About me</h2>
          <p>
            Locked and loaded good optics target rich environment pass the mayo, appeal to the
            client, sue the vice president . creativity requires you to murder your children
            programmatically, nor ensure to follow requirements when developing solutions.
          </p>
          <button
            class="flex flex-shrink-0 bg-primary hover:bg-blue-700 border-blue-800 hover:border-blue-700 text-sm font-medium border-4 text-white py-1 px-2 rounded"
            type="submit"
          >
            Read more
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
      <div class="skills-container">
        <div class="skills-container__title">
          <h2 class="text-primary text-5xl">Skills</h2>
        </div>
        <section class="flex">
          <div>
            <h3>Javascript</h3>
            <ul>
              <li>Vue</li>
              <li>Angular</li>
              <li>RxJS</li>
            </ul>
          </div>
          <div>
            <h3>Javascript</h3>
            <ul>
              <li>Vue</li>
              <li>Angular</li>
              <li>RxJS</li>
            </ul>
          </div>
        </section>
      </div>
      <img alt="wave-2" class="wave-bottom w-full" src="/images/uploads/wave-2.svg" />
    </div>

    <div class="container flex flex-col relative mx-auto">
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

.wave-top {
  margin-bottom: -40px;
  z-index: -1;
  position: relative;
}

.wave-bottom {
  margin-bottom: -300px;
}

.about-container {
  padding: 8rem;
  display: flex;
  padding-left: 0rem;
  margin-top: -0.25rem;
  margin-left: 6rem;
  height: 640px;
  background-image: url(/images/uploads/blob-1.svg);
  background-repeat: no-repeat;
  background-position: bottom;
  justify-content: center;
  align-items: center;
  object-fit: contain;
  width: 905px;
  p {
    max-width: 470px;
    font-size: 24px;
    margin-bottom: 2rem;
  }
}

.skills-container {
  background-image: url(/images/uploads/blob-2.svg);
  background-repeat: no-repeat;
  height: 820px;
  width: 865px;
  margin-right: 120px;
  margin-left: auto;

  .skills-container__title {
    background-image: url(/images/uploads/blob-small.svg);
    background-repeat: no-repeat;
    background-position: left;
    margin-left: 55px;
    height: 400px;
    width: 330px;
    display: flex;
    justify-content: center;
    align-items: center;
    h2 {
      margin-bottom: 2rem;
      margin-right: 2rem;
    }
  }
}
</style>
