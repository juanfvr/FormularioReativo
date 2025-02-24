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
    font-size: .8em;
    color: red;
  }
</style>