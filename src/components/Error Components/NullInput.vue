<script setup>
defineProps({
  isNull: Boolean,
})
</script>

<template>
  <span v-if="isNull">Campo em branco</span>
</template>

<style scoped>
  span {
    color: red;
  }
</style>