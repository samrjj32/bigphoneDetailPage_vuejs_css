<script setup>
import Counter from "./blocks/ProductCounter.vue";
</script>


<template>
  <div class="right-section">
    <div class="right-header">
      <h2>SAMSUNG</h2>
      <span>Hurry Limited stock</span>
    </div>
    <h1>Samsung Galaxy S23 Ultra 5G</h1>
    <h2>£800</h2>
    <span class="strick-bar"></span>
    <ul class="info-list">
      <li>
        <p class="info-label">Sim:</p>
        <p class="info-value">Dual Sim</p>
      </li>
      <li>
        <p class="info-label">Condition:</p>
        <p class="info-value">Like new</p>
      </li>
      <li>
        <p class="info-label">Color:</p>
        <p class="info-value">Lavender</p>
      </li>
      <li>
        <p class="info-label">Network:</p>
        <p class="info-value">Unlocked</p>
      </li>
      <li>
        <p class="info-label">Storage:</p>
        <p class="info-value">512GB</p>
      </li>
    </ul>

    <span class="strick-bar"></span>
    <Counter />
    <button class="add-to-cart-button">Add to Basket</button>

    <!-- Your content goes here -->
  </div>
</template>



<style scoped>
.right-section {
  flex: 1;
  /* width: 50%; */
  box-sizing: border-box;
  padding: 20px;
}

.right-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.right-header h2 {
  color: #9e9e9e;
}
.right-header span {
  color: #7dad92;
}

.strick-bar {
  display: block;
  width: 100%;
  height: 1px;
  background-color: #ccc;
  margin: 10px 0;
}

.info-list {
  list-style-type: none;
  padding: 20px 0px;
  padding-bottom: 20px;
  padding-top: 20px;
}

.info-list li {
  display: flex;
  justify-content: start;
  margin-bottom: 10px;
}

.info-label {
  margin-right: 10px;
}
.add-to-cart-button {
  margin-top: 10px;
  width: 100%;
  background-color: #ffd812;
  color: #333;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}
/* Responsive Styles */
@media (max-width: 768px) {
  .right-section {
    width: 100%;
  }

  .info-list li {
    /* flex-direction: column; */
    margin-bottom: 15px;
  }

  .info-label {
    margin-right: 0;
    margin-bottom: 5px;
  }
}
</style>
