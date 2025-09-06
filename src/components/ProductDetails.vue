<template>
  <div class="product-container">
    <div class="image-gallery">
      <div class="main-image-wrapper">
        <div class="main-image">
          <img :src="selectedImage" alt="Main Product" />
        </div>
        
        <div class="image-counter">
          {{ currentIndex + 1 }}/{{ images.length }}
        </div>
      </div>

      <div class="thumbnail-row">
        <img
          v-for="(img, index) in images"
          :key="index"
          :src="img"
          :class="{ active: selectedImage === img }"
          @click="selectedImage = img"
          class="thumbnail"
          alt="Thumbnail"
        />
      </div>
    </div>

    <!-- Right Section (Details) -->
    <div class="product-details">
      <h2 class="title">{{ product.title }}</h2>
      <div class="rating">
        <img src="/images/stars.svg" alt="star" class="main-image" />
        <img src="/images/stars.svg" alt="star" class="main-image" />
        <img src="/images/stars.svg" alt="star" class="main-image" />
        <img src="/images/stars.svg" alt="star" class="main-image" />
        <img src="/images/lightstar.svg" alt="star" class="main-image" />
        <span> 4.5 ┃ ({{ product.reviews }} Reviews)</span>
      </div>

      <div class="amount">
        <div class="price">
          <p>Priceoye Price</p>
          <span class="current">
            <span class="smallrs">Rs</span> {{ product.price }}</span
          >
          <span class="old">
            <span class="smallrs"> Rs </span> {{ product.oldPrice }}</span
          >
          <span class="discount">{{ product.discount }}% OFF</span>
        </div>

        <div class="availability">
          Availability: <br /><span
            ><b>{{ product.stock }}</b></span
          >
        </div>
      </div>

      <div class="colors">
        <p>Colors:</p>
        <div class="Black-color">
          <img src="/images/img1.webp" alt="Black Color" />
          <p>Black</p>
        </div>
      </div>

      <div class="gift-wrap-box">
        <div class="gift-wrap-left">
          <input type="checkbox" />
          <div class="gift-text">
            <h4>Add Gift Wrap</h4>
            <div class="cost">Cost: Rs 199</div>
            <div class="sub-text">Make it Memorable - Add Gift Wrapping!</div>
          </div>
        </div>
        <div class="gift-image">
          <img src="/images/gift_wrap.webp" alt="Gift Wrap" />
        </div>
      </div>
      <div class="action-buttons">
        <button class="add-to-cart">Add to Cart</button>
        <button class="compare">Compare</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";
import "../assets/product.scss";

const product = {
  title: "M10 TWS Wireless Bluetooth Earbuds",
  reviews: 2608,
  price: 749,
  oldPrice: 2499,
  discount: 70,
  stock: "In Stock",
  colors: ["#000000", "#ffffff"],
};

const images = [
  "/images/img1.webp",
  "/images/img2.webp",
  "/images/img3.webp",
  "/images/img4.webp",
  "/images/img1.webp",
  "/images/img2.webp",
];

const selectedImage = ref(images[0]);

// ✅ Compute current index based on selectedImage
const currentIndex = computed(() => images.indexOf(selectedImage.value));
</script>
