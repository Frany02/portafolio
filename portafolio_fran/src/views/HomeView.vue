<template>
  <section class="hero">
     <video ref="videoplayer" class="hero__video" autoplay loop preload="auto" playsinline>
        <source src="../assets/befo.mp4" type="video/mp4">
     </video>
     <div class="hero__content">
        <h1 class="hero__title"></h1>
        <p class="hero__text"></p>
     </div>
  </section>
</template>
<script>
  export default {
    name: 'HomeView',
    components: {
   
    },
    mounted() {
      this.$refs.videoplayer.addEventListener('loadedmetadata', this.playVideo);
    },
    methods: {
      playVideo() {
        this.$refs.videoplayer.play();
      }
    }
  }
</script>
<style scoped>
  body {
  margin: 0;
  }
  .hero {
  width: 100%;
  position: relative;
  padding-bottom: 56.25%; /* Relación de aspecto 16:9 (9 dividido por 16, multiplicado por 100) */
  }
  .hero__video{
  position: absolute;
  width: 100%;
  height: 100%;
  object-fit: cover;
  left: 0;
  top: 0;
  }
  .hero__content{
  position: absolute;
  transform: translate(-50%, -50%);
  top: 50%;
  left: 50%;
  color: #FFF;
  z-index: 1;
  }
  .hero__title{
  color: #FFF;
  font-size: 64px;
  font-size: 32px;
  margin-bottom: 20px;
  }
  .hero__text{
  color: #FFF;
  font-size: 20px;
  margin-bottom: 20px;
  }
  .hero__link{
  color: #333;
  font-size: 20px;
  background-color: #FFF;
  border: 2px solid #FFF;
  text-decoration: none;
  padding: 10px;
  border-radius: 2px;
  }
  .container{
  background-color: gray;
  }
  @media screen and (min-width: 768px) {
  .hero__title{
  font-size: 64px;
  }
  }
  @media screen and (min-width: 992px) {
  .hero__title{
  font-size: 72px;
  }
  }
</style>