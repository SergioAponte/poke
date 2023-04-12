<template>
    <div class="contenedor_principal">
        <div><h2>{{ nombre }}</h2></div>
        <div>
            <div><img :src="url" alt=""></div>
            <div class="cuadro_habilidades">
                <div class="squirils">
                    <h2>Status</h2>
                    <p v-for="i in response.stats"  :key="i.stat.name"  >{{ i.stat.name }}</p>
                </div>
                <div class="habilities">
                    <h2>abilities</h2>
                    <p v-for=" i in response.abilities" :key="i.ability.name">{{ i.ability.name }}</p>
                </div>
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
            url:''
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
        console.log(this.response)
    },
}


}
</script>

<style>
p{
    color: black;
}
</style>