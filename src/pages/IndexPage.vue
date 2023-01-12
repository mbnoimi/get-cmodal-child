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
          <q-input
            id="jassem"
            v-model="text"
            label="Standard"
            ref="focusSubmit"
          />

          <q-input v-model="text2" label="Another one" />
        </template>
      </modal>
    </Teleport>
  </q-page>
</template>

<script setup lang="ts">
import { ref, nextTick } from 'vue';
import Modal from 'src/components/ModalDialog.vue';

let showModal = ref(false);
const focusSubmit = ref(null);
const dlg = ref(null);
const text = ref('');
const text2 = ref('');

async function doModal(event) {
  showModal.value = true;
  await nextTick();
  if (event) {
    console.log(focusSubmit.value.focus());
  }
}
</script>
