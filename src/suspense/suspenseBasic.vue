<script setup lang="ts">
import { defineAsyncComponent } from 'vue';
import Loading from '../components/Loading.vue';
import ErrorComponente from '../components/ErrorComponente.vue';

/*const DataViewAsync = defineAsyncComponent(
  () => import('../components/DataView.vue')
);*/

const DataViewAsync = defineAsyncComponent({
  loader: () => {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        //  resolve(import('../components/DataView.vue'));
        reject();
      }, 900);
    });
  },
  errorComponent: ErrorComponente,
});
</script>

<template>
  <Suspense timeout="0">
    <template #default>
      <DataViewAsync />
    </template>
    <template #fallback>
      <Loading />
    </template>
  </Suspense>
</template>
