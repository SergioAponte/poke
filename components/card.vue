<template>
    <nuxt-link :to="nombre">
        <div class="card_tarjetas">
            <div class="fondo">
                <img :src="url" alt="">
                <p class="name">{{ nombre }}</p>
            </div>
        </div>
    </nuxt-link>
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
    height: 400px;
    width: 350px;
    border: 3px solid  black;
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
    height: 70%;
    width: 70%;
}
p{
    color: white;
    font-size: 40px;
}

</style>