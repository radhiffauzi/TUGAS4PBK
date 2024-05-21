<template>
  <div>
    <h1>Hello</h1>
    <ChildComponent @send-data="displayData">
      <template v-slot:additional-content>
        <p>PBK Radhif</p>
        <GrandchildComponent @send-data="handleGrandchildData" />
      </template>
    </ChildComponent>
    <p v-if="dataFromChild">Data from Child: {{ dataFromChild }}</p>
    <p v-if="dataFromGrandchild">Data from Grandchild: {{ dataFromGrandchild }}</p>
  </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue';
import GrandchildComponent from './GrandchildComponent.vue';

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
