<template>
  <button class="button" @click="$emit('action')">{{ props.content }}</button>
</template>
  
  <script setup>
  const props = defineProps({
    content: String
  })
  </script>
  
  <style scoped>
  .button {
    padding: 1rem 1.6rem;
    border-radius: 0.6rem;
    border: none;
  
    font-size: 1rem;
    font-weight: bold;
    text-transform: uppercase;

    transition: 200ms;
  }

  .button:hover {
    opacity: 0.6;
  }

  .button:active {
    opacity: 0.4;
  }
  </style>