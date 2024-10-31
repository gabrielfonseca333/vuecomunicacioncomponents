<template>
  <nav class="navbar navbar-expand-lg bg-body-tertiary">
    <div class="container-fluid">
      <button @click="redirectToHome()" class="btn btn-outline-dark">
        Home 🏠
      </button>
      <ul id="menu" v-for="num in numerosAleatorios" :key="num">
        <li class="nav-item">
          <router-link :to="'/tablaMultiplicar/' + num"
            >Tabla Multiplicar | {{ num }}</router-link
          >
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: "MenuTablaMultiplicar",

  data() {
    return {
      numerosAleatorios: [],
    };
  },

  methods: {
    redirectToHome() {
      this.$router.push("/");
    },
  },

  mounted() {
    for (let i = 0; i < 5; i++) {
      const numeroAleatorio = Math.floor(Math.random() * 100) + 1; // Genera un número entre 1 y 100
      this.numerosAleatorios.push(numeroAleatorio);
    }
  },
};
</script>

<style>
ul#menu li {
  display: inline;
}
</style>