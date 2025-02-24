<script setup>
import {ref} from "vue";
import NullInput from "@/components/Error Components/NullInput.vue";

defineProps({
  inputValue: Boolean,
  label: String,
})

const input = defineModel();
</script>

<template>
  <div>
    <label for="">{{ label }}</label>
    <input
        type="text"
        autocomplete="false"
        v-model="input"
        :style="!inputValue ? 'border: 2px solid red' : 'border: 2px solid var(--primary-color)' "
    >
    <NullInput :is-null="!input" />
  </div>
</template>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  width: 100%;
  color: var(--primary-color);
}

input {
  padding: .4em;
  border-radius: 8px;
  outline: none;
}
</style>