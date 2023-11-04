<template>
  <div>
    <p>{{ text }}</p>
    <p>{{ textComputed }}</p>
    <button @click="clickHandler">Нажми</button>
  </div>
</template>

<script setup lang="ts">
import { ref, computed, watch } from "vue";

const text = ref("Тестовый текст");

const textComputed = computed(() => {
  if (text.value === "Тестовый текст") return "Ага";
  return "Неа";
});

function clickHandler() {
  text.value = "Нажата кнопка";
}

watch(text, () => {
  console.log("Текст поменялся");
});
</script>

<style scoped>
p {
  color: white;
}
</style>
