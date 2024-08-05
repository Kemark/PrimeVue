<script setup lang="ts">
import { ref } from 'vue';
import DdCard from '@/components/Card.vue';

const msg = ref('');
</script>

<template>
  <main>
    <h1>Playground</h1>
    <InputText v-model="msg" />
    <p>{{ msg }}</p>
    <dd-card isClickabl></dd-card>
  </main>
</template>

<style scoped></style>
