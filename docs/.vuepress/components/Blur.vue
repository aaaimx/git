<template>
  <div class="demo" v-blur="false">
    <p>Hello world!!!</p>
  </div>
</template>

<script>
export default {
  directives: {
    blur: {
      bind (el, binding) {
        // DOM manipulation
        el.style.filter = !binding.value ? 'blur(3px)' : '(none)'
        el.style.filter = !binding.value ? 'not-allowed' : 'inherit'
        console.log(binding.value)
        el.querySelectorAll('a').forEach(element => {
          if (!binding.value) {
            element.setAttribute('disabled', true)
          } else {
            element.removeAttribute('disabled')
          }
        })
      }
    }
  }
}
</script>
