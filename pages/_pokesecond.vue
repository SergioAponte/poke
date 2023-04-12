<template>
    <vistasecond/>
</template>
<script>
import vistasecond from '~/components/vistasecond.vue'
export default{
components: { vistasecond },
    name:"PokemonPage",
    mounted(){
        console.log(this.$route)
    }
}
</script>