<template>
  <div class="padre">
    <h1>Comic</h1>

    <div class="form-container" >
        <form v-on:submit.prevent="createComic()">
            <input class="form-control" type="text" placeholder="Titulo" v-model="comicForm.titulo">
            <input class="form-control" type="text" placeholder="Descripcion" v-model="comicForm.descripcion">
            <input class="form-control" type="text" placeholder="Imagen" v-model="comicForm.imagen">
            <input class="form-control" type="number" placeholder="Año" v-model="comicForm.year">
            <button class="btn btn-dark">Crear Comic</button>
        </form>
    </div>

    <div v-if="comicFavorito"  class="tarjeta" style="border: 1px solid gold; color: gold; margin-bottom: 30px">
        <h1>⭐{{comicFavorito.titulo}}⭐</h1>
    </div>
    
    
    <div v-for="(comic, index) in comics" :key="comic">
        <ComicComponent 
        :comic="comic"
        :index="index"
         v-on:seleccionarFavorito="seleccionarFavorito"
         v-on:deleteComic="deleteComic"
         />
    </div>
    
  </div>
  
</template>

<script>
import ComicComponent from './ComicComponent.vue'
export default {
    name: "ComicsComponent",
    components:{
        ComicComponent
    },

    methods:{
        createComic(){
            this.comics.push(this.comicForm);
        },

        seleccionarFavorito(comic){
            console.log("⭐Este es el favorito: " + comic.titulo)
            this.comicFavorito = comic
        },
        
        deleteComic(index){
            this.comics.splice(index, 1);
        }
    },


    data(){
        return{
            comicFavorito:null,
            comicForm:{
                titulo:"",
                imagen:"",
                descripcion:"",
                year:0
            },
            
            comics: [
                {
                titulo: "Spiderman",
                imagen:
                    "https://3.bp.blogspot.com/-i70Zu_LAHwI/T290xxduu-I/AAAAAAAALq8/8bXDrdvW50o/s1600/spiderman1.jpg",
                descripcion: "Hombre araña"
                , year: 1997
                },
                {
                titulo: "Wolverine",
                imagen:
                    "https://images-na.ssl-images-amazon.com/images/I/51c1Q1IdUBL._SX259_BO1,204,203,200_.jpg",
                descripcion: "Lobezno"
                , year: 2003
                },
                {
                titulo: "Guardianes de la Galaxia",
                imagen:
                    "https://upload.wikimedia.org/wikipedia/en/thumb/3/35/Gotg_2.jpg/220px-Gotg_2.jpg",
                descripcion: "Yo soy Groot"
                , year: 2006
                },
                {
                titulo: "Avengers",
                imagen:
                    "https://d26lpennugtm8s.cloudfront.net/stores/057/977/products/ma_avengers_01_01-891178138c020318f315132687055371-640-0.jpg",
                descripcion: "Los Vengadores"
                , year: 1993
                },
                {
                titulo: "Spawn",
                imagen:
                    "https://i.pinimg.com/originals/e1/d8/ff/e1d8ff4aeab5e567798635008fe98ee1.png",
                descripcion: "Al Simmons"
                , year: 2000
                },
                {
                titulo: "Batman",
                imagen:
                    "https://www.comicverso.com/wp-content/uploads/2020/06/The-Killing-Joke-657x1024.jpg",
                descripcion: "Murcielago"
                , year: 2001
                }
            ]

        }
    }
}
</script>

<style>
    @import "./../assets/css/styles"
</style>