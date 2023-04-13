<template>
    <!-- <div class="w-full h-screen bg-indigo-300">
        <p>asdfwe</p>
    </div> -->
    <div class="principal w-full">
        <h1>Poke Dex</h1>
        <main class="contenido">
            <form action="" @submit.prevent="search" ><input id="busqeda" type="text" placeholder="Buscar Pokemon"  v-model="search"></form>
            
                <div class="main_tarjeta_contenedor">
                    <div  v-for="i in response" :key="i.name">
                        <card :nombre="i.name" :url="i.sprites.other.dream_world.front_default"/>
                    </div>
                </div>
        </main>
    </div>
</template>
<script>


export default {
    name: 'PokePage',
    data(){
        return{
            response:[
            ],
            // search:''
        }
    },
    mounted(){
        this.getinfo()
        // this.buscar()
    },
    methods:{
        async getinfo(){
            for(let j=1;j<20;j++){
                const {data}= await this.$axios.get(`pokemon/${j}`)
                this.response.push(data)
                console.log(this.response)
            }
        },
        // buscar(){
        //     for(let i=0;i<this.response.length;i++){
        //         if(this.data[i].name==this.search){
        //             this.$router.push(`/${this.search}`)
        //         }
        //         console.log(this.search)
        //     }
        // }
        // props:{
        //     url:{
        //         type:String

                
        //     }
        // }
    }
}
</script>


<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
} 
/* template{
    height: 100vh;
    width: 100vw;
} */

.principal{
    width: 100vw;
    height: auto;
    border: 1px solid;
    background-color: aqua;
    position: absolute;
}

/* .dad{
    display: flex;
    flex-wrap: wrap;
} */

.main_tarjeta_contenedor{
    width: 100%;
    height: auto;
    display: flex;
    flex-wrap: wrap; 
    gap: 20px;
}


h1{
    width: 90%;
    height: 10%;
    font-size: 50px;
    background-color: white;
    border: 1px solid;
    border-radius: 7px ;
    text-align: center;
    margin: 20px 10px;
}
main{
    width: 100%;
    height: 90%;
    display: flex;
    flex-direction: column;
    gap: 20px;
    padding: 20px 10px;
}
input{
    width: 200px;
    height: 30px;
    border: 1px solid black;
    border-radius: 7px;
}
/* .tarjetas{
    height: 300px;
    width: 250px;
    border: 1px solid;
    background-color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 5px;
}
.fondo{
    height: 95%;
    width: 95%;
    background-color: red;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    border-radius: 5px;
    border: 1px solid;
}

img{
    height: 90%;
    width: 90%;
}
p{
    color: white;
} */
P{
    color: white;
}


</style>