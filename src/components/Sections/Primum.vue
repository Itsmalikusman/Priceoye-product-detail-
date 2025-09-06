<template>
  
  <div class="similar-products">
    <h2>Upgrade to Premium</h2>
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
  </div>
</template>

<script setup>
const products = [
  {
    image: "/images/primum1.webp",
    title: "PR-3 Touch screen Tws Earbuds",
    desc: "1,849"
  },
  {
    image: "/images/primum2.webp",
    title: "DX-02 TWS Earbuds",
    desc: "1,849"
  },
  {
    image: "/images/primum3.webp",
    title: "STN-28 Cat Claws Headphone",
    desc: "1,599"
  },
  {
    image: "/images/primum4.webp",
    title: "YD MINI Wireless Earbuds",
    desc: "1,499"
  }
];
</script>
