<template>
  <div class="container py-5">
    <div class="card shadow">
      <div class="card-body">
        <h1 class="card-title mb-4">Registro de Usuario</h1>

        <form @submit.prevent>
          <div class="mb-3">
            <label class="form-label">Nombre:</label>
            <input
              type="text"
              class="form-control"
              v-model="nombre"
              :class="{ 'is-invalid': mostrarResumen && !nombre }"
            />
          </div>

          <div class="mb-3">
            <label class="form-label">Correo electrónico:</label>
            <input
              type="email"
              class="form-control"
              v-model="correo"
              :class="{ 'is-invalid': mostrarResumen && !correo }"
            />
          </div>

          <div class="mb-3">
            <label class="form-label">Edad:</label>
            <input
              type="number"
              class="form-control"
              v-model="edad"
              :class="{ 'is-invalid': mostrarResumen && !edad }"
            />
          </div>

          <div class="d-flex gap-2">
            <button
              class="btn btn-primary"
              @click="mostrarResumen = true"
              :disabled="!formularioCompleto"
            >
              Enviar
            </button>
            <button class="btn btn-secondary" type="button" @click="limpiarFormulario">
              Limpiar
            </button>
          </div>
        </form>

        <div v-if="mostrarResumen && formularioCompleto" class="alert alert-success mt-4">
          <h5>Resumen:</h5>
          <p><strong>Nombre:</strong> {{ nombre }}</p>
          <p><strong>Correo:</strong> {{ correo }}</p>
          <p><strong>Edad:</strong> {{ edad }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Formulario',
  data() {
    return {
      nombre: '',
      correo: '',
      edad: '',
      mostrarResumen: false
    };
  },
  computed: {
    formularioCompleto() {
      return this.nombre && this.correo && this.edad;
    }
  },
  methods: {
    limpiarFormulario() {
      this.nombre = '';
      this.correo = '';
      this.edad = '';
      this.mostrarResumen = false;
    }
  }
};
</script>

