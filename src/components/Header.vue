<script setup>
import logo from "../../src/assets/images/logo.webp";
</script>

<template>
  <div class="header">
    <img :src="logo" :alt="'logo'" />
  </div>
</template>

<style scoped>
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 60px;
  width: 100%;
  background: #fff;
}

.header img {
  max-width: 100px;
  max-height: 100px;
  width: auto;
  height: auto;
  margin-left: 15%;
}
</style>
