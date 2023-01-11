<template>
  <q-page class="row items-center justify-evenly">
    <q-btn
      id="show-modal"
      @click="showModal = true"
      color="primary"
      icon="mail"
      label="Show Modal"
    />

    <Teleport to="body">
      <!-- use the modal component, pass in the prop -->
      <modal :show="showModal" @close="showModal = false">
        <template #header>
          <q-btn id="jassem" label="Check Port" ref="focusSubmit" />
        </template>
      </modal>
    </Teleport>
  </q-page>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';
import Modal from 'src/components/ModalDialog.vue';

const showModal = ref(false);
const focusSubmit = ref(null);

onMounted(() => {
  ////// ERROR
  console.log(focusSubmit.value.label);
});
</script>
