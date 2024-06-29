<script setup lang="ts">
import { defineAsyncComponent, type Ref, ref } from 'vue';
import Loading from '../components/Loading.vue';
import ErrorComponente from '../components/ErrorComponente.vue';

const DataViewAsync = defineAsyncComponent(
  () => import('../components/DataView.vue')
);
const DataViewAsynctwo = defineAsyncComponent(
  () => import('../components/DataViewTwo.vue')
);

const swichtRef: Ref<boolean> = ref(true);

const swicht = () => {
  swichtRef.value = !swichtRef.value;
};

console.log('aa');
</script>

<template>
  <button @click="swicht">cambiar</button>
  <Suspense>
    <template #default>
      <component :is="swichtRef ? DataViewAsync : DataViewAsynctwo">
      </component>
    </template>
    <template #fallback>
      <Loading />
    </template>
  </Suspense>
</template>
