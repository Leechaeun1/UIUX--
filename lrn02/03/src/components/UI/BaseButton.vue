<!-- css로 컴포넌트 VS vue로 컴포넌트 -->
<!-- vue에선 컴포넌트 하나로만 재사용 가능해야함 -->

<script setup>
import { computed } from 'vue'
const props = defineProps({
  variant: {
    type: String,
    default: 'primary',
  },
})
const buttonClass = computed(() => {
  return {
    'btn-primary': props.variant === 'primary',
    'btn-outline': props.variant === 'outline',
    'btn-pill': props.variant === 'pill',
  }
})
</script>
<template>
  <button :class="buttonClass">
    <slot>Button</slot>
  </button>
</template>
<style scoped>
/* 버튼 */
.btn-primary {
  background-color: #ff8db5;
  color: white;
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 0.375rem;
  cursor: pointer;
  margin-right: 10px;
}

.btn-outline {
  background: none;
  border: 2px solid #ff8db5;
  color: #ff8db5;
  padding: 0.5rem 1rem;
  border-radius: 0.375rem;
  cursor: pointer;
  margin-right: 10px;
}

.btn-pill {
  background-color: #ff8db5;
  color: white;
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 50%;
  cursor: pointer;
}
</style>
