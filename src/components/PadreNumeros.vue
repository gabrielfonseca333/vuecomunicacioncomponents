<template>
  <div style="border: 3px solid red; padding: 20px; color:red; border-radius: 16px">
    <h1>Padre Numeros</h1>
    <h2>{{total}}</h2>
    <ul v-for="num in numeros" :key="num">
        <HijoNumero :numerillo="num" v-on:sumarNumero="sumarNumero"/>
    </ul>
  </div>
</template>

<script>
import HijoNumero from './HijoNumero.vue'

export default {
    name: "PadreNumeros",
    components:{
        HijoNumero
    },
    data(){
        return{
            numeros:[77,27,1000,365,4],
            total:0
        }
    },
    methods:{

        sumarNumero(numero){
            this.total = this.total + numero
            
        }

    }
}
</script>

<style>

</style>