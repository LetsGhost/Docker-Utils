<template>
  <main v-if="currentComponent === ''"></main>
  <component :is="currentComponent"></component>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import LoadPage from './Load.vue'
import ExportPage from './Export.vue'
import Dashboard from './Dashboard.vue'

export default defineComponent({
  components: {
    LoadPage,
    ExportPage,
    Dashboard
  },
  setup() {
    const currentComponent = ref('Dashboard')

    return {
      currentComponent
    }
  }
})
</script>
