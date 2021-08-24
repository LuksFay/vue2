<template>
    <div>
        <h1>Gallery</h1>

        <router-link :to="{name: 'photos', params: {id: item}}" 
        v-for="(item, index) of fotosArreglo" :key="index">
            <button>Foto {{item}}</button>
        </router-link>
        <photo />
        <button @click="home">Home</button>
        <button @click="anterior">Anterior</button>
        <button @click="siguiente">Siguiente</button>
    </div>
</template>

<script>

import photo from '@/components/Photographie.vue'
export default {
    components:{
        photo
    },
    data(){
        return{
            fotosArreglo: [1,2,3]
        }
    },
    methods: {
        home(){
            this.$router.push('/')
        },
        anterior(){
            this.$router.go(-1)
        },
        siguiente(){
            this.$router.go(+1)
        }
    },
}
</script>