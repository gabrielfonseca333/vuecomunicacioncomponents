<template>
  <div style="border: 1px solid blue; color: blue; width: 50%; margin: 0 auto; padding: 20px">
    <h1>{{this.numerillo}}</h1>
    <button @click="sumarNumero" class="btn btn-outline-primary">Sumar {{this.numerillo}}</button>
  </div>
</template>

<script>
export default {
    name: "HijoNumero",
    props:["numerillo"],
    methods:{

        sumarNumero(){
            this.$emit("sumarNumero", this.numerillo)
        }

    }
    
}
</script>

<style>

</style>