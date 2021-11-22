<template>
  <section class="container content aboutMePage" id="about-me" tabindex="0">
    <div class="aboutMeContent">
      <div class="photo-holder">
        <img loading="lazy" class="my-photo" :src="AboutMe.Image" :alt="AboutMe.ImageAlt" width="200" height="200">
        <span v-if="!isLoading" class="my-photo-loading loading-effect"></span>
      </div>
      <div class="description-holder">
        <h2 class="title" v-text="AboutMe.Title"></h2>
        <p class="description" v-html="AboutMe.Description"></p>
      </div>
    </div>
  </section>
</template>

<script>
import { AboutMe } from "/Data.json"

export default {
  data(){
    return{
      AboutMe: AboutMe,
      Image: null,
      isLoading: false
    }
  },
  mounted() {
    this.Image = document.querySelector(".my-photo");
    this.Image.addEventListener("load", () => this.isLoading = true )
  }
}
</script>