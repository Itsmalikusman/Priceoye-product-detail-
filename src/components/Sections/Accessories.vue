<template>
  <div class="accessories-section similar-products">
    <h2 class="section-title">Connect Your Accessories</h2>
    <div class="accessories-videos">
      <div class="accessories-video" v-for="(video, index) in videos" :key="index">
        <iframe
          :src="video"
          frameborder="0"
          allowfullscreen
        ></iframe>
      </div>
    </div>
  </div>
</template>

<script setup>
const videos = [
  "https://www.youtube.com/embed/j4Z9bAflJWY?si=CbBv_sgpEfLJNEIe", 
  "https://www.youtube.com/embed/tJqz-74QI14?si=IXoryJVoX7NPlTBy"  
];
</script>
