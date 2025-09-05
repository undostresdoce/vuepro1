<template>
  <div class="d-flex flex-column min-vh-100">
    <main class="flex-grow-1">
      <Formulario />
    </main>

    <footer class="bg-dark text-white text-center py-3">
      <small>&copy; Camila Collado - Daniel Paredes - Jesús Pérez</small>
    </footer>
  </div>
</template>

<script>
import Formulario from './components/Formulario.vue';

export default {
  components: {
    Formulario
  }
};
</script>