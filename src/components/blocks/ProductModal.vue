<script setup>
import ImageSection from "../blocks/ImageContainer/Image.vue";
import LeftSectionNew2 from "../LeftSectionNew2.vue";
import VideoSection from "../blocks/VideoContainer/Video.vue";
</script>

<template>
  <div v-if="isModalOpen" class="modal" :class="{ 'modal-open': isModalOpen }">
    <div class="modal-content">
      <div class="tab-switcher">
        <button @click="switchTab(0)" :class="{ active: activeTab === 0 }">
          Videos
        </button>
        <button @click="switchTab(1)" :class="{ active: activeTab === 1 }">
          Images
        </button>
        <span class="close" @click="toggleModal">&times;</span>
      </div>

      <!-- Modal content here -->
      <VideoSection :currentTab="activeTab === 0" />
      <ImageSection :currentTab="activeTab === 1" :currentIndex="activeIndex" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isModalOpen: Boolean,
    selectedImage: Object,
    activeIndex: Number,
  },
  data() {
    return {
      activeTab: 0, // Track the active tab index
    };
  },
  methods: {
    toggleModal() {
      this.$emit("toggleModal");
    },
    switchTab(index) {
      this.activeTab = index; // Set the active tab index
    },
  },
};
</script>

<style scoped>
/* Modal styling */
.modal {
  display: none;
  position: fixed;
  z-index: 1000;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgba(0, 0, 0, 0.4);
}

.modal-open {
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal-content {
  background-color: #fafafa;
  padding: 10px; /* Adjusted padding to 10px */
  border: 1px solid #888;
  min-width: calc(100% - 20px);
  max-height: calc(100% - 20px);
  overflow: hidden; /* Allow scrolling if content exceeds modal size */
  box-sizing: border-box; /* Include padding in width/height calculation */
  margin: auto; /* Center the modal */
}

.close {
  color: #aaaaaa;
  font-size: 28px;
  font-weight: bold;
  position: absolute;
  top: 10px;
  right: 20px;
  cursor: pointer;
}

.tab-switcher {
  margin-top: 10px;
  border-bottom: 1px solid #ccc; /* Add thin bottom border */
}
.tab-switcher button.active {
  border-bottom: 2px solid rgb(240 147 5); /* Color for active border bottom */
}

.tab-switcher button {
  background-color: transparent;
  border: none;
  outline: none;
  cursor: pointer;
  padding: 10px 20px;
}

.tab-switcher button.active {
  /* background-color: #ccc; */
}
</style>
