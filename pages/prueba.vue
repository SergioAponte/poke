<template>
    <div> 
        <p>">{{ nombre }}</p>
        <img v-if="mostrar" src="https://www.shutterstock.com/image-vector/good-job-stampvector-illustration-260nw-773726719.jpg" alt="">
        <button @click="cambiar">cambiar nombre</button></div>
</template>
<script>
export default{
    name:'PruebaPage',
    data() {
    return{
        nombre:'Sergio Andrés',
        mostrar: true
    }
    },
    methods: {
        cambiar(){
            if(this.nombre=='Sergio Andrés'){
                this.nombre='Aponte Lamus'
                this.mostrar=false
            }else{
                this.nombre='Sergio Andrés'
                this.mostrar=true
            }
        }
    }
}
</script>

<style>
    button{
        background-color: red;
    }
</style>