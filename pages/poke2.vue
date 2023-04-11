<template>
    <div class="container">
        <h1>Poke Dex</h1>
        <main class="contenido">
            <input id="busqeda" type="text">
            <div class="tarjeta1 tarjetas">
                <!-- <div class="fondo">
                    <img src="https://spng.pngfind.com/pngs/s/348-3483440_drianas-chimchar-imagenes-de-pokemon-chimchar-hd-png.png" alt="">
                    <p class="name">Charmander</p>
                </div> -->
            </div>
        </main>
    </div>
</template>
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
.__layout{
    width: 0;
}

.container{
    width: 150vw;
    height: 100vh;
    border: 1px solid;
    background-color: aqua;
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
.tarjetas{
    height: 300px;
    width: 250px;
    border: 1px solid;
    background-color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 5px;
}
</style>