<template>
  <main v-if="currentComponent === ''">
    <p>Choose an option:</p>
    <button @click="currentComponent = 'LoadPage'">Load .tar file</button>
    <button @click="currentComponent = 'ExportPage'">Export image</button>
  </main>
  <component :is="currentComponent"></component>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import LoadPage from './Load.vue'
import ExportPage from './Export.vue'

export default defineComponent({
  components: {
    LoadPage,
    ExportPage
  },
  setup() {
    const currentComponent = ref('')

    return {
      currentComponent
    }
  }
})
</script>
