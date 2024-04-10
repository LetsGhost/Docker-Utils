<template>
  <div>
    <button @click="goBack"></button>
    <p>Export image</p>
  </div>
</template>

<script setup lang="ts">
import {ref} from 'vue'

const goBack = () => {
    currentComponent.value = ''
}
</script>
