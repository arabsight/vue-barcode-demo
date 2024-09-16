<template>
  <main>
    <div ref="cardRef">
      <SVGBarcode :value="562" />
    </div>

    <button @click="handlePrint">Print</button>
  </main>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import SVGBarcode from '@/components/SVGBarcode.vue';
import { useVueToPrint } from 'vue-to-print';

const cardRef = ref();

const { handlePrint } = useVueToPrint({
  content: cardRef,
  documentTitle: 'card',
  removeAfterPrint: true
});
</script>

<style scoped>
@page {
  margin: 10px;
  /* background-color: blueviolet;
  width: 300px; */
}
</style>
