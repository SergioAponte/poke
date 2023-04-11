<template>
    <div class="container">
        <h1>Poke Dex</h1>
        <main class="contenido">
            <input id="busqeda" type="text" placeholder="Buscar Pokemon">
            <div v-for="i in response" :key="i.name">
                <card :nombre="i.name" :url="i.sprites.front_default"/>
            </div>
        </main>
    </div>
</template>
<script>
export default {
    name: 'IndexPage',
    data(){
        return{
            response:[
            ]
        }
    },
    mounted(){
        this.getinfo()
    },
    methods:{
        async getinfo(){
            for(let j=1;j<20;j++){
                const {data}= await this.$axios.get(`pokemon/${j}`)
                this.response.push(data)
                console.log(this.response)
            }
        },
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
#__layout{
    width: 0;
}

.container{
    width: 100vw;
    height: 100vh;
    border: 1px solid;
    background-color: aqua;
}

/* .dad{
    display: flex;
    flex-wrap: wrap;
} */

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


</style>