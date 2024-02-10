<script setup>
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "./components/HelloWorld.vue";
import LeftSection from "./components/LeftSection.vue";
import RightSection from "./components/RightSection.vue";
import Header from "./components/Header.vue";
import LeftSectionNew from "./components/LeftSectionNew.vue";
</script>

<template>
  <Header />

  <div class="card-wrapper">
    <div class="card">
      <LeftSectionNew />
      <!-- <LeftSection /> -->
      <RightSection />
      <!-- <RouterView /> -->
    </div>
  </div>
</template>

<style scoped>
.card-wrapper {
  max-width: 1100px;
  margin: 0 auto;
  padding-top: 50px;
}

.card {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-gap: 1.5rem;
}

@media only screen and (max-width: 768px) {
  .card-wrapper {
    padding-top: 30px;
  }
  .card {
    grid-template-columns: 2fr;
  }
  .card > :last-child {
    grid-row-start: 2; /* Move the last child (RightSection) to the second row */
  }
}
</style>

