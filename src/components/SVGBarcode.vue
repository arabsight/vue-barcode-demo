<template>
  <svg id="barcode"></svg>
</template>

<script setup lang="ts">
import { onMounted } from 'vue';
import JsBarcode from 'jsbarcode';

const props = defineProps<{ value: string | number }>();

onMounted(() => {
  JsBarcode('#barcode', props.value.toString(), {
    format: 'code39',
    height: 50,
    displayValue: false,
    margin: 0
  });
});
</script>

<style scoped></style>
