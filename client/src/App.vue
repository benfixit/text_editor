<template>
  <div>
    <button type="button" @click="showModal">Show Modal</button>
    <TheModal v-show="isModalVisible" @close="closeModal">
      <template v-slot:header>This is the App Header</template>
      <template v-slot:footer>This is the App footer</template>
    </TheModal>
  </div>
</template>

<script>
import TheModal from './components/TheModal.vue';

  export default {
    data() {
        return {
            isModalVisible: false
        };
    },
    methods: {
        showModal() {
            this.isModalVisible = true;
        },
        closeModal() {
            this.isModalVisible = false;
        }
    },
    components: { TheModal }
}
</script>

<style scoped>
  .controls {
      flex: 1;
      border: thin solid green;
  }

  .content {
      flex: 4;
      padding: 20px 40px;
      display: flex;
  }

  .content > textarea {
      flex: 3;
      background-color: #ffffff;
      outline: none;
      border: thin solid #aaaaaa;
      padding: 100px;
  }

  .content > aside {
      flex: 1;
  }
</style>