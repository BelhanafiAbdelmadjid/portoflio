<template>
    <nav class="nav-border-on"  >
        <!-- :class="{'nav-border-on' : !scrolledBoolean ,'nav-border-off' : scrolledBoolean  }" -->
        <p @click="scrollTo('intro')" style="cursor: pointer;" :class="{'nav-p-left' : !scrolledBoolean ,'nav-p-center' : scrolledBoolean  }"  >JIDSU</p>
        <p @click="scrollTo('contact')" style="cursor: pointer;" :class="{'nav-p-right' : !scrolledBoolean }" v-if="!scrolledBoolean" >Contact</p>
    </nav>
    <section class="back main_section" >
        <Hello></Hello>
    </section>

    <main>
        <about></about>
        <skills></skills>
        <contact></contact>
    </main>

</template>

<script setup>
import Hello from './views/Hello.vue';
import about from "./views/about.vue"
import skills from "./views/skills.vue"
import contact from "./views/contact.vue"
import { ref, onMounted } from 'vue'

const scrolledBoolean = ref(false)

function detectScrolling(){
    window.addEventListener('scroll', function() {
    var scrolled = window.scrollY;
    if (scrolled >= window.innerHeight-50) {
        scrolledBoolean.value = true;
    } else {
        scrolledBoolean.value = false;
    }
    });
}
detectScrolling();

function scrollTo(To){
    document.getElementById(To).scrollIntoView({ behavior: 'smooth', block: 'start' });
}

</script>


<style scoped>
.nav-border-on{
    border-bottom: 1px solid ;
    border-color: var(--borders-colors-light);
}
.nav-border-off{
    border: none;
    border-color: none;
}
.back{
    
    position: fixed;
    top: 0;
    left: 0;
    z-index: -999;
    width: 100vw;

    height: calc(100vh -  var(--main-nav-bar-height) );
    margin-top: var(--main-nav-bar-height);

    transition: 
        height 0.25s ease;
}
nav{
    
    position: fixed;
    top:0;
    z-index: 999;

    height : var(--main-nav-bar-height);
    width: 100%;
    
    padding : 0px 5vw ;
    box-sizing: border-box;
    
    display: flex;
    align-items: center;
    

    background-color: var(--dark-gray);
    
    
    font-size: var(--medieum-text-size);


    transition: 
        font-size 0.25s ease,
        height 0.25s ease;
}
nav p{
    position: fixed;
    transition: 
    left 0.5s ease-out;
}
.nav-p-right{
    right :0;
}
.nav-p-center{
    left: 50%;
    transform: translateX(-50%);
}
.nav-p-left{
    left :0;
}
main{
    padding-top: 100vh;
    box-sizing: border-box;

    width: 100vw;
    box-sizing: border-box;

    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;

    overflow: hidden;
}


@media (max-width: 720px) {
    nav{
        font-size: var(--medieum-text-size-phone);
        height : var(--main-nav-bar-height-mobile);
    }
    .back{
        height: calc(100vh -  var(--main-nav-bar-height-mobile) );
        margin-top: var(--main-nav-bar-height-mobile);
    }
}
</style>
