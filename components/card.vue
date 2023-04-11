<template>
    <div class="card_tarjetas">
        <div class="fondo">
            <img :src="url" alt="">
            <p class="name">{{ nombre }}</p>
        </div>
    </div>
</template>
<script>

export default {
    name: 'IndexPage',
    props:{
        nombre:{
            type:String,
            required: true
        },
        url:{
            type:String,
            required: true
        }
    }
}
</script>
<style>

.card_tarjetas{
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
}

</style>