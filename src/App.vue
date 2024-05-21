<template>
  <div>
    <h1>HELLO PENGGEMAR VESPA</h1>
    <ChildComponent @send-data="displayData">
      <template v-slot:additional-content>
        <p>TUGAS PBK RADHIF FAUZI</p>
        <GrandchildComponent @send-data="handleGrandchildData" />
      </template>
    </ChildComponent>
    <p v-if="dataFromChild">Data from Child: {{ dataFromChild }}</p>
    <p v-if="dataFromGrandchild">Data from Grandchild: {{ dataFromGrandchild }}</p>
  </div>
</template>

<script>
import ChildComponent from './components/ChildComponent.vue';
import GrandchildComponent from './components/GrandChildComponent.vue';

export default {
  components: {
    ChildComponent,
    GrandchildComponent
  },
  data() {
    return {
      dataFromChild: null,
      dataFromGrandchild: null
    };
  },
  methods: {
    displayData(data) {
      this.dataFromChild = data;
    },
    handleGrandchildData(data) {
      this.dataFromGrandchild = data;
    }
  }
};
</script>
