<template>
  <div class="hijo tarjeta" style="margin-Bottom: 30px">
    <h1>{{comic.titulo}}</h1>
    <img :src="comic.imagen">
    <hr>
    <p>{{comic.descripcion}}</p>
    <h3 :class="{
        rojo: comic.year <= 2000,
        verde: comic.year >2000

    }">{{comic.year}}</h3>
    <button @click="seleccionarFavorito()" class="btn btn-dark">⭐  Favourite</button>
    <br>
    <button @click="deleteComic()" class="btn btn-outline-danger">❌ Eliminar</button>
</div>
</template>

<script>
export default {
    name: "ComicComponent",
    props:["comic", "index"],
    data(){
        return{
            
        }
    },
    methods:{
        seleccionarFavorito(){
            this.$emit("seleccionarFavorito", this.comic)
        },

        deleteComic(){
            this.$emit("deleteComic", this.index)
        }
    }
}
</script>

<style>

</style>