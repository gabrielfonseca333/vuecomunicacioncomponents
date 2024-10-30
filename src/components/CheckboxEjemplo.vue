<template>
  <div>
    <h1>Suma Checkbox</h1>
    <div  v-for="num in numeros" :key="num">
        <input v-model="num.selected" type="checkbox"><span>{{num.valor}}</span>
    </div>
    <button @click="sumar()" class="btn btn-dark">Sumar</button>
    <br>
    <div v-if="sumaTotal !== null">
        <h2>Suma total: {{sumaTotal}}</h2>
    </div>
        
  </div>
</template>

<script>
export default {
    name:"CheckboxEjemplo",
    data(){
        return{
            numeros:[
                {valor: 5, selected:false},
                {valor: 6, selected:false},
                {valor: 9, selected:false},
                ],
                sumaTotal:null
        }
    },
    methods:{

        sumar(){
            
            this.sumaTotal = this.numeros.filter(n => n.selected==true); //para filtrar
            this.sumaTotal = this.numeros.reduce((suma, numero) => suma + numero.valor, 0); //para sumar


        }

    }
}
</script>

<style>

</style>