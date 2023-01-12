<template>
  <q-page class="row items-center justify-evenly">
    <q-btn
      id="show-modal"
      @click="doModal"
      color="primary"
      icon="mail"
      label="Show Modal"
    />

    <Teleport to="body">
      <!-- use the modal component, pass in the prop -->
      <modal :show="showModal" @close="showModal = false" ref="dlg">
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

let showModal = ref(false);
const focusSubmit = ref(null);
const dlg = ref(null);

function doModal(event) {
  showModal.value = true;
  if (event) {
    ////// ERROR
    console.log(focusSubmit.value);
  }
}
</script>
