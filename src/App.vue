<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue';
import suspenseBasic from './suspense/suspenseBasic.vue';
import SuspenseAndComponent from './suspense/SuspenseAndComponent.vue';
import SuspenseAndComponetTwo from './suspense/SuspenseAndComponetTwo.vue';
</script>

<template>
  <HelloWorld />
  <suspenseBasic />
  <hr />
  <SuspenseAndComponent />
  <hr />
  <SuspenseAndComponetTwo />
</template>

<style scoped></style>
