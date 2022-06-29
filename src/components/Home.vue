<template>
    <div id="home" >
        <HeaderApp/>
        <div class="introduction-text">
            <MyCanvas />
            <Canvass/>
            <p>My name is Amine BAHEDDI</p>
            <p>and I am a </p>
            
        </div>
    </div>
</template>

<script>
import HeaderApp from './Header.vue'
import Canvass from './canvass.vue'
import MyCanvas from './myNewCanvas.vue'


export default {
    name: 'home',
    components:{
    HeaderApp,
    MyCanvas,
    Canvass,
},
    data:() => {

        return {
            mySkills: ["Developer", "Designer"],
        }
    },
    methods: {
    },
    
}
</script>

<style scoped>
#home{
    width: 100%;
    /* height: 100vh; */
    text-align: center;
}

</style>