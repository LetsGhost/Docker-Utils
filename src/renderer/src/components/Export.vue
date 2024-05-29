<template>
  <div>
    <p>Export image</p>
    <div v-for="(image, index) in images" :key="index" style="display: flex; justify-content: space-between; align-items: center;">
      <img :src="image.src" :alt="image.alt" />
      <button @click="exportImage(image)">Export</button>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';

const images = ref([]);

const getImages = () => {
  window.electron.send('getAllImages')
  window.electron.receive('allImages', (receivedImages) => {
    images.value = receivedImages;
  })
}

onMounted(getImages);

const exportImage = (image) => {
  // Add your image export logic here
}
</script>