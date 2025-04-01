<script setup>
import { computed } from 'vue'
const props = defineProps({
  variant: {
    type: String,
    default: 'success',
  },
})
const alertClass = computed(() => {
  return {
    'alert-success': props.variant === 'success',
    'alert-warning': props.variant === 'warning',
    'alert-error': props.variant === 'error',
  }
})
</script>
<template>
  <div :class="alertClass">
    <slot>알림 메시지입니다.</slot>
  </div>
</template>
<style scoped>
/* 알림창 */
.alert-success {
  background-color: #dcfce7;
  color: #15803d;
  border-left: 4px solid #128f4a;
  padding: 0.75rem;
  margin-bottom: 0.5rem;
}
.alert-warning {
  background-color: #fbdd82;
  color: black;
  border-left: 4px solid #fc963c;
  padding: 0.75rem;
  margin-bottom: 0.5rem;
}
.alert-error {
  background-color: #faa58d;
  color: #000000;
  border-left: 4px solid #f55e40;
  padding: 0.75rem;
  margin-bottom: 0.5rem;
}
</style>
