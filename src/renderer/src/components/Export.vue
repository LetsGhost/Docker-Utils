<template>
  <div>
    <p>Export image</p>
    <button @click="getImages">Get images</button>
  </div>
</template>

<script setup lang="ts">
const getImages = () => {
  window.electron.send('getAllImages')
  window.electron.receive('allImages', (images) => {
    console.log(images)
  })
}
</script>
