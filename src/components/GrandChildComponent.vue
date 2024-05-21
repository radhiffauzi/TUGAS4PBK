<template>
  <div>
    <h3>Grandchild Component</h3>
    <button @click="sendDataToParent">Send Data to Parent</button>
  </div>
</template>

<script>
export default {
  methods: {
    sendDataToParent() {
      this.$emit('send-data', 'This is data from the grandchild');
    }
  }
};
</script>
