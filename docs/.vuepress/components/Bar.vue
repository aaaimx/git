<template>
  <p class="demo">
    <button @click="showAlert">Click me!!</button>
  </p>
</template>

<script>
  export default {
    methods: {
      showAlert() {
        this.$emit('showAlert')
      }
    }
  }
</script>
