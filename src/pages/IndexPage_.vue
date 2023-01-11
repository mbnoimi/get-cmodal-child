<template>
  <q-page class="row items-center justify-evenly">
    <q-btn id="jassem" label="Check Port" ref="focusSubmit" />
  </q-page>
</template>

<script setup>
import { ref, onMounted } from 'vue';
const focusSubmit = ref(null);
onMounted(() => {
  console.log(focusSubmit.value);
  console.log(focusSubmit.value.label);
});
</script>
