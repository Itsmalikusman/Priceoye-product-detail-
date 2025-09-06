<template>
  <div class="sections-wrapper">
    <!-- Headings Row -->
    <nav class="sections-nav">
      <ul>
        <li v-for="section in sections" :key="section.id">
          <a :href="'#' + section.id">{{ section.title }}</a>
        </li>
      </ul>
    </nav>

    <!-- Actual Sections -->
    <div class="sections-content">
      <section id="similar-products"><SimilarProducts /></section>
      <section id="highlights"><Highlights /></section>
      <section id="specifications"><Specifications /></section>
      <section id="box"><BoxContents /></section>
      <section><Primum /></section>
      <section id="accessories"><Accessories /></section>
      <section id="reviews"><Reviews /></section>
      <section id="faqs"><FAQs /></section>
    </div>
  </div>
</template>

<script setup>
import "../assets/product.scss"

import SimilarProducts from "./Sections/SimilarProducts.vue"
import Highlights from "./Sections/Highlights.vue"
import Specifications from "./Sections/Specifications.vue"
import BoxContents from "./Sections/BoxContents.vue"
import Accessories from "./Sections/Accessories.vue"
import FAQs from "./Sections/FAQs.vue"
import Primum from "./Sections/primum.vue"

const sections = [
  { id: "similar-products", title: "Similar Products" },
  { id: "highlights", title: "Highlights" },
  { id: "specifications", title: "Specifications" },
  { id: "box", title: "What’s In The Box" },
  { id: "accessories", title: "Connect Your Accessories" },
  { id: "faqs", title: "FAQs" }




]
</script>
