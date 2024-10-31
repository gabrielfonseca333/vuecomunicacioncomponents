<template>
  <div class="tarjeta">
    <h1>Tabla Multiplicar del {{numeroData}}</h1>
    <div>
        <table class="table table-hover">
        <thead>
            <tr class="table-dark">
                <th>Operacion</th>
                <th>Resultado</th>
            </tr>
        </thead>
        <tbody>
            <!-- aqui -->
            <tr v-for="i in 10" :key="i">
                <td>{{i}} * {{numeroData}}</td>
                <td>{{i*numeroData}}</td>
            </tr>
        </tbody>
    </table>
    </div>
  </div>
</template>

<script>
export default {
    name: "TablaMultiplicar",
    data(){
        return{
            numeroData: 0,
        }
    },
    mounted(){
        this.numeroData = this.$route.params.numero;
    },
    watch:{
        '$route.params.numero' (nextVal, oldVal){
            if(nextVal != oldVal){
                this.numeroData = parseInt(this.$route.params.numero);
            }
        }
    },
    methods:{

    }
}
</script>

<style>
    @import "./../assets/css/styles";
</style>