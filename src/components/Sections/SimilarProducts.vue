<template>
  
  <div class="similar-products">
    <h2>Products That Go Together</h2>
    <div class="similar-card-grid">
      <div class="similar-card" v-for="(product, index) in products" :key="index">
        <img :src="product.image" :alt="product.title" />
        <h3>{{ product.title }}</h3>
        <p>
          <sup>
            Rs
          </sup>
          {{ product.desc }}
        </p>
      </div>
    </div>
    <div class="empty"></div>
    <div class="similer-details">
      <div class="item-details">
        <img src="/images/warranty-feature.svg" alt="warranty-feature">
        <strong>No Warranty</strong>
        <span>Brand Warranty</span>
      </div>
      <div class="item-details">
        <img src="/images/easy-feature.svg" alt="warranty-feature">
        <strong>Easy Returns</strong>
        <span>Free of Charge</span>
      </div>
      <div class="item-details">
        <img src="/images/video-shooting-camera.svg" alt="warranty-feature">
        <strong>Packaging Video</strong>
        <span>See Your Product</span>
      </div>
      <div class="item-details">
        <img src="/images/shipping-feature.svg" alt="warranty-feature">
        <strong>Fast Delivery</strong>
        <span>All Over Pakistan</span>
      </div>
    </div>
  </div>
</template>

<script setup>
const products = [
  {
    image: "/images/watch.webp",
    title: "TW8 Ultra Smart Watch",
    desc: "2,099"
  },
  {
    image: "/images/charger.webp",
    title: "Mars MQ-5 18W Charger",
    desc: "699"
  },
  {
    image: "/images/speaker.webp",
    title: "1Hora Bocina Bluetooth Speaker BOC241N",
    desc: "4249"
  },
  {
    image: "/images/trimer.webp",
    title: "Trimmer X TM-6556 3  in 1 Hair clipper",
    desc: "1799"
  }
];
</script>
