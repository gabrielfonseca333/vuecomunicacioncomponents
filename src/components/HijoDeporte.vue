<template>
  <div style="border: 1px solid blue; color: blue; width: 50%; margin: 0 auto">
    <h1>{{this.nombredeporte}}</h1>
    <button @click="marcarFavoritoHijo" class="btn btn-primary">Marca favorito</button>
  </div>
</template>

<script>
export default {
    name: "HijoDeporte",
    props:["nombredeporte"],
    mounted(){
        console.log(this.nombredeporte)
    },
    methods:{

        marcarFavoritoHijo(){
            console.log("Soy el hijo")
            //DEBEMOS REALIZAR LA LLAMADA AL PADRE
            //DICHA LLAMADA SE REALIZA MEDIANTE string "nombreDelMetodoParent"
            //PARA ENVIAR INFORMACION SE REALIZA CON COMAS POR CADA PARAMETRO
            //QUE TENGA LA RECEPCION
            this.$emit("marcarFavorito", this.nombredeporte);
            
        }

    }

}
</script>

<style>

</style>