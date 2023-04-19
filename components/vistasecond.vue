<template>
    <div class="contenedor_principal">
        <h2>{{ nombre }}</h2>
        <div class="general">
            <div class="imagen_general"><img :src="url" alt=""></div>
            <div class="cuadro_habilidades">
                <div class="squirils">
                    <h3 class="status">Status</h3>
                    <p v-for="i in response.stats"  :key="i.stat.name"  >{{ i.stat.name }}:  {{ i.base_stat }}</p>
                </div>
                <div class="habilities">
                    <h3>abilities</h3>
                    <p v-for=" i in response.abilities" :key="i.ability.name">{{ i.ability.name }}</p>
                </div>
            </div>
            <div class="imagenes_segundarias">
                <img :src="imagenes.back_default" alt="">
                <img :src="imagenes.back_shiny" alt="">
                <img :src="imagenes.front_shiny" alt="">
                <img :src="imagenes.front_default" alt="">
            </div>
        </div>
    </div>
</template>

<script>
export default{
    name:'PokeApi',
    data(){
        return{
            response:[],
            nombre:this.$route.params.pokesecond,
            url:'',
            imagenes:{}
        }
},
    mounted(){
        console.log(this.$route),
        this.getinfo()

    },
    methods:{
        async getinfo(){
        const {data}= await this.$axios.get(`pokemon/${this.$route.params.pokesecond}`)
        this.response=(data)
        this.url=this.response.sprites.other.dream_world.front_default
        this.imagenes=this.response.sprites

        console.log(this.response)
    },
}


}
</script>

<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}  

.contenedor_principal{
    height: 100vh;
    width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    background-image: url(../img/X8ms9l2.webp);
    background-repeat: no-repeat;
    background-size: cover;
}

.contenedor_principal .general{
    display: grid;
    height: 90%;
    width: 100%;
    grid-template-areas: 
    'parte1  parte2 '
    'parte3 parte3 '
    ;
}

.imagen_general{
    grid-area: parte1;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-right: 7px;
}

.imagen_general img{
    height: 70%;
    width: 70%;
}


.cuadro_habilidades{
    grid-area: parte2;
    display: grid;
    grid-template-areas: 
    'parte1 parte2'
    ;
    gap: 5px;
}

.squirils{
    grid-area: parte1;
    border: 5px solid;
    width: 400px;
    border-radius: 7px;
    background-color: red;

}
.habilities{
    grid-area: parte2;
    border: 5px solid black;
    background-color: rgb(241, 233, 233);
    width: 400px;
    border-radius: 7px;
    display: flex;
    align-items: center;
    flex-direction: column;
}

.habilities p{
    color: black;

}


.imagenes_segundarias{
    grid-area: parte3;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 40px;
}

.imagenes_segundarias img{
    height: auto;
    width: 150px;
    border: 3px solid;
    background-color: rgba(255, 255, 255, 0.623);
    border-radius: 7px;
}

h2{
    width: 90%;
    height: 10%;
    font-size: 45px;
    background-color: white;
    border: 1px solid;
    border-radius: 7px ;
    text-align: center;
    margin: 20px 10px;
    display: flex;
    justify-content: center;
    align-items: center;
}

h3{
    width: 90%;
    height: 10%;
    font-size: 35px;
    background-color: white;
    border: 1px solid;
    border-radius: 7px ;
    text-align: center;
    margin: 20px 10px;
    display: flex;
    justify-content: center;
    align-items: center;
}

p{
    font-size: 30px;
    color: white;

}
</style>