<script setup>
import { defineAsyncComponent } from 'vue'

// import TheWelcome from '../components/TheWelcome.vue'

// 직접 lazy load 처리하기 => About.vue에서 불필요한 파일 다운받지 않음 !
const TheWelcome = defineAsyncComponent(() => import('../components/TheWelcome.vue'))
</script>

<template>
  <main>
    <TheWelcome />
  </main>
</template>
