<script setup>
import { computed } from 'vue'
const props = defineProps({
  variant: {
    type: String,
    default: 'success',
  },
})
const badgeClass = computed(() => {
  return {
    'badge-success': props.variant === 'success',
    'badge-number': props.variant === 'number',
  }
})
</script>
<template>
  <span :class="badgeClass">
    <slot>badge</slot>
  </span>
</template>
<style scoped>
/* 배지 */
.badge-success {
  background-color: #ff8db5;
  color: white;
  padding: 0.25rem 0.5rem;
  font-size: 0.625rem;
  /* 9999px : 가장 자연스럽게 깎기 위한 사이즈 */
  border-radius: 9999px;
}

.badge-number {
  background-color: red;
  color: white;
  border-radius: 50%;
  padding: 0.25rem 0.5rem;
  font-size: 0.625rem;
}
</style>
