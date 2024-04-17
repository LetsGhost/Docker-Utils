<template>
  <div>
    <button @click="currentComponent = 'LoadPage'">Load Page</button>
    <button @click="currentComponent = 'ExportPage'">Export Page</button>
    <component :is="currentComponent"></component>
  </div>
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
