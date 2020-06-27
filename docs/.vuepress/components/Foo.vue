<template>
  <div>
    <Bar @showAlert="show" />
  </div>
</template>

<script>
export default {
  methods: {
    show () {
      alert('Hello world!!!')
    }
  }
}
</script>
