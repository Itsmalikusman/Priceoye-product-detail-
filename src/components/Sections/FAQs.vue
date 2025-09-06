<template>
  <div class="similar-products">
    <h2 class="section-title">
      Questions About M10 TWS Wireless Bluetooth Earbuds
    </h2>
  </div>
  <div class="faq-section">
    <div class="faq-list">
      <div
        v-for="(faq, index) in faqs"
        :key="index"
        class="faq-item"
        :class="{ active: faq.isOpen }"
      >
        <div class="faq-question" @click="toggleFaq(index)">
          <span>Q. {{ faq.question }}</span>
          <svg
            class="chevron-icon"
            :class="{ rotated: faq.isOpen }"
            width="20"
            height="20"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
          >
            <polyline points="6,9 12,15 18,9"></polyline>
          </svg>
        </div>

        <transition name="slide-fade">
          <div v-if="faq.isOpen" class="faq-answer">
            <div class="faq-answer-content">
              <p>{{ faq.answer }}</p>
              <div class="like-dislike-section">
                <button
                  class="like-btn"
                  :class="{ active: faq.userLiked }"
                  @click="toggleLike(index)"
                >
                  <svg
                    width="16"
                    height="16"
                    viewBox="0 0 24 24"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                  >
                    <path
                      d="M14 9V5a3 3 0 0 0-3-3l-4 9v11h11.28a2 2 0 0 0 2-1.7l1.38-9a2 2 0 0 0-2-2.3zM7 22H4a2 2 0 0 1-2-2v-7a2 2 0 0 1 2-2h3"
                    ></path>
                  </svg>
                  {{ faq.likes }} Likes
                </button>
                <button
                  class="dislike-btn"
                  :class="{ active: faq.userDisliked }"
                  @click="toggleDislike(index)"
                >
                  <svg
                    width="16"
                    height="16"
                    viewBox="0 0 24 24"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                  >
                    <path
                      d="M10 15v4a3 3 0 0 0 3 3l4-9V2H5.72a2 2 0 0 0-2 1.7l-1.38 9a2 2 0 0 0 2 2.3zm7-13h2.67A2.31 2.31 0 0 1 22 4v7a2.31 2.31 0 0 1-2.33 2H17"
                    ></path>
                  </svg>
                  {{ faq.dislikes }} Dislikes
                </button>
              </div>
            </div>
          </div>
        </transition>
      </div>
    </div>

    <div class="ask-question-section">
      <h3>Ask a question</h3>
      <textarea
        v-model="newQuestion"
        placeholder="Write question here"
        class="question-textarea"
      ></textarea>
      <button class="ask-question-btn">Ask Question</button>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const newQuestion = ref("");

const faqs = ref([
  {
    question: "Return policy is available",
    answer:
      "We provide a 3-day check warranty; if your product is damaged or faulty, you may file a claim and we will replace it. Please find the link of our Return Policy for details : https://priceoye.pk/return-policy",
    isOpen: false,
    likes: 15,
    dislikes: 6,
    userLiked: false,
    userDisliked: false,
  },
  {
    question: "It s original",
    answer:
      "Yes, this product is 100% original and comes with manufacturer warranty.",
    isOpen: false,
    likes: 15,
    dislikes: 6,
    userLiked: false,
    userDisliked: false,
  },
  {
    question:
      "Salaam Mai ny Website se ye earbuds order kiye but 1 Mai. He. Kam. Nhi. Kr. Rhy Light. To on H. But. Voice Arhi. Ab. Btayen Kya Kesy wo thk Hogi",
    answer:
      "Dear Customer, To ensure that we can provide you with the most effective and efficient assistance, we kindly request that you lodge a complaint on our website",
    isOpen: false,
    likes: 6,
    dislikes: 7,
    userLiked: false,
    userDisliked: false,
  },
  {
    question: "Does it contain power bank",
    answer:
      "For price, specifications, availability, and other details regarding your desired product, please visit our website at : https://priceoye.pk",
    isOpen: false,
    likes: 4,
    dislikes: 2,
    userLiked: false,
    userDisliked: false,
  },
  {
    question: "Call suni ja skti in py",
    answer: "Earbuds with built-in microphones and Bluetooth connectivity are often capable of making calls if they are paired with a compatible device like a smartphone. For more details please visit the product's official website",
    isOpen: false,
    likes: 3,
    dislikes: 2,
    userLiked: false,
    userDisliked: false,
  },
]);

const toggleFaq = (index) => {
  faqs.value[index].isOpen = !faqs.value[index].isOpen;
};

const toggleLike = (index) => {
  const faq = faqs.value[index];
  if (faq.userLiked) {
    faq.likes--;
    faq.userLiked = false;
  } else {
    if (faq.userDisliked) {
      faq.dislikes--;
      faq.userDisliked = false;
    }
    faq.likes++;
    faq.userLiked = true;
  }
};

const toggleDislike = (index) => {
  const faq = faqs.value[index];
  if (faq.userDisliked) {
    faq.dislikes--;
    faq.userDisliked = false;
  } else {
    if (faq.userLiked) {
      faq.likes--;
      faq.userLiked = false;
    }
    faq.dislikes++;
    faq.userDisliked = true;
  }
};
</script>
