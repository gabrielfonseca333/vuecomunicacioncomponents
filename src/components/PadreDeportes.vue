<template>
  <div style="border: 3px solid red; padding: 20px; color:red; border-radius: 16px">
    <h1>Padre Deportes</h1>
    <div style="border: 2px solid gold; margin: 10px">
        <h2 style="color: gold;"> FAVORITO: {{favorito}} </h2>
    </div>
    <ul v-for="sport in deportes" :key="sport">
        <HijoDeporte :nombredeporte="sport" v-on:marcarFavorito="marcarFavorito"/>
    </ul>
    
  </div>
</template>

<script>
import HijoDeporte from './HijoDeporte.vue'

export default {
    name: "PadreDeportes",
    components:{
        HijoDeporte
    },
    data(){
        return{
            deportes:["Bolas Criollas", "Tiro al arco", "Ping Pong", "Padel"],
            favorito:null
        }
    },

    methods:{

        marcarFavorito(nombre){
    
            console.log("Yo soy tu padre")
            this.favorito = nombre
        }

    }
}
</script>

<style>

</style>