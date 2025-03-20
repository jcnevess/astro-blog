<script setup>
import { ref } from "vue";

const props = defineProps({
  messages: { type: Array, required: true },
});

const greeting = ref(props.messages[0]);

function randomMessage() {
  return props.messages[Math.floor(Math.random() * props.messages.length)];
}
</script>

<template>
  <div>
    <h3>{{ greeting }}! Thank you for visiting!</h3>
    <button @click="() => (greeting = randomMessage())">New Greeting</button>
  </div>
</template>

<style scoped>
button {
  cursor: pointer;
}
</style>
