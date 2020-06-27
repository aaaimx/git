<template>
  <div class="container">
    <header>
      <slot name="header"><h1>Aquí podría ir un título de página</h1> </slot>
    </header>
    <main>
      <slot>visite: {{ url }} para mas información </slot>
    </main>
    <footer>
      <slot name="footer">Aquí va alguna información de contacto </slot>
    </footer>
  </div>
</template>

<script>
export default {
  // props: ['url']
  props: {
    url: {
      type: String,
      default: 'No url'
    }
  }
}
</script>
