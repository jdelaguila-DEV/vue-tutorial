<template>
  <button class="btn btn-success" @click="increment">Counter {{ counter }}</button>
</template>

<script setup lang="ts">

import { ref } from 'vue';

const counter = ref(0);

const increment = () => counter.value++;

defineProps<{
  color: string;
}>();

</script>

<style scoped></style>