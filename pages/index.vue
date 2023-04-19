<template>
    <login v-if="login"/>
    <div v-else class="principal w-full">
        <h1>Poke Dex</h1>
        <main class="contenido">
            <form action="" @submit.prevent="buscar" >
                <input id="busqeda" type="text" placeholder="Buscar Pokemon"  v-model="search">
            </form>
            <div class="main_tarjeta_contenedor">
                <div  v-for="i in response" :key="i.name">
                    <card :nombre="i.name" :url="i.sprites.other.dream_world.front_default"/>
                </div>
            </div>
            <div class="botones">
                <button @click="atras" class="atras"><img class="atras" src="../img/arrow-icon-arrows-sign-black-arrows-free-png.webp" alt=""></button>
                <button @click="next" class="next"><img class="adelante" src="../img/arrow-icon-arrows-sign-black-arrows-free-png.webp" alt=""></button>
            </div>
        </main>
    </div>
</template>
<script>


export default {
    name: 'PokePage',
    data(){
        return{
            response:[],
            responsesegundo:[],
            search:'',
            contador:1,
            login:true
        }
    },
    mounted(){
        this.getinfo()
        this.buscar()
    },
    methods:{
        async getinfo(){
            try{
                for(let j=1;j<100;j++){
                        const {data}= await this.$axios.get(`pokemon/${j}`)
                        this.responsesegundo.push(data)
                    }
                if(this.contador==1){
                    for(let j=1;j<20;j++){
                        const {data}= await this.$axios.get(`pokemon/${j}`)
                        this.response.push(data)
                        this.login=false
                    }
                }else if(this.contador==2){
                    for(let j=21;j<41;j++){
                            const {data}= await this.$axios.get(`pokemon/${j}`)
                            this.response.push(data)
                            this.login=false
                        }
                }else if(this.contador==3){
                    for(let j=42;j<60;j++){
                            const {data}= await this.$axios.get(`pokemon/${j}`)
                            this.response.push(data)
                            this.login=false
                        }

                }else if(this.contenedor==4){
                    for(let j=61;j<81;j++){
                            const {data}= await this.$axios.get(`pokemon/${j}`)
                            this.response.push(data)
                            this.login=false
                        }
                }else{
                    for(let j=82;j<100;j++){
                            const {data}= await this.$axios.get(`pokemon/${j}`)
                            this.response.push(data)
                            this.login=false
                        }
                }
                setTimeout(()=>{
                    this.login=false
                },2000)    
            }catch(e){
                console.e('error');
            }
    },
        buscar(){
            for(let i=0;i<this.response.length;i++){
                if(this.responsesegundo.name==this.search){
                    this.$router.push(`/${this.search}`)
                }
            }
        },
        next(){
            this.contador++
            this.getinfo()
            this.response=[]
        },
        atras(){
            this.contador--
            this.getinfo()
            this.response=[]
        }
        
    }
}
</script>


<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
} 


.principal{
    width: 100vw;
    height: auto;
    border: 1px solid;
    background-image: url(../img/DVMT-6OXcAE2rZY.jpg.afab972f972bd7fbd4253bc7aa1cf27f.jpg);
    position: absolute;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

}


.main_tarjeta_contenedor{
    width: 100%;
    height: auto;
    display: flex;
    flex-wrap: wrap; 
    gap: 20px;
    justify-content: center;
    align-items: center;
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
    height: 80%;
    display: flex;
    flex-direction: column;
    gap: 20px;
    padding: 20px 10px;
}
input{
    width: 250px;
    height: 40px;
    border: 1px solid black;
    border-radius: 7px;
    margin-left: 50px;
    font-size: 20px;
    background-color: rgb(252, 252, 209);
}
P{
    color: white;
}
.botones{
    height: 10%;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 100px;
}

.botones img{
    height: auto;
    width: 60px;
}

.atras{
    transform: rotate(88deg);
}


</style>