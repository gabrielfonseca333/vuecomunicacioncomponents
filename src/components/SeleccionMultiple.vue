<template>
  <div>
    <h1>Selección Multiple</h1>
    <div class="tarjeta">
      <select class="form-select" v-model="clienteSeleccionado" multiple>
        <option v-for="client in clientes" :key="client">{{ client }}</option>
      </select>
      <br />
      <button @click="mostrarClientes()" class="btn btn-dark">Mostrar</button>
      <div>
        <div v-for="client in clienteMostrado" :key="client">
          <h3>{{ client }}</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SeleccionMultiple",
  components: {},
  data() {
    return {
      clientes: ["PedroSinPelos", "SandraInnerExperience", "MAZE FUNNELS"],
      clienteSeleccionado: [],
      clienteMostrado: [],
    };
  },
  methods: {
    mostrarClientes() {
      this.clienteMostrado = this.clienteSeleccionado;
    },
  },
};
</script>

<style>
@import "./../assets/css/styles"
</style>