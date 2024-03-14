<script setup>
import { ref, onMounted } from 'vue'

const props =defineProps({
  header : String ,
  index : Number
})
const scrolledBoolean = ref(false)
function detectScrolling(){
    window.addEventListener('scroll', function() {
    var scrolled = window.scrollY;
    console.log(props.index)
    if (scrolled >= (window.innerHeight*props.index)-50) {
        console.log("arrived!")
        scrolledBoolean.value = true;
    } else {
        console.log("not yet!")
        scrolledBoolean.value = false;
    }
    });
}
detectScrolling();
</script>

<template>
    <section class="holder"  :class="{ 
        'being-relative' : scrolledBoolean ,
        'not-being-relative' : !scrolledBoolean,
        'holder-radius' : props.index < 2,
        'holder-border-top' : props.index > 1
        }" >
        <div class="about-me"  :class="{ 'being-nav' : scrolledBoolean , 'not-being-nav' : !scrolledBoolean }" >
            <span>
                {{ header }}
            </span>
        </div>
        <header style="opacity: 0;"  >
            {{ header }}
        </header>

        <slot name="content" ></slot>

    </section>
</template>

<style scoped>
.holder-border-top{
    border-top: solid 1px var(--dark-gray);
}
.about-me{
    display: flex;
    justify-content: center;
    align-items: center;

    font-size: var(--medieum-text-size);

    z-index: 9999;

    transition: 
        left 0.25s ease;

}
.not-being-nav{
    position: absolute;
    left: 50%;
    top:0;
    transform: translateX(-50%);
    z-index: 99999;

    padding-top: calc(var(--main-nav-bar-height) + 10px);
    
    color: var(--dark-gray);
    text-decoration: underline;
    
    width: 100%;
}
.being-nav{
    position: fixed;
    top: var(--main-nav-bar-height);
    left:0;

    width: 100%;
    height: var(--main-nav-bar-height);
    background-color: var(--dark-gray);
    text-decoration: none;

    color: var(--dark-gray);
    text-decoration: none;

    animation: aboutEntering 0.5s ;

}
.being-nav span{
    color: var(--light-text-color);
    text-decoration: none;
    
}

.holder-radius{
    border-top-right-radius: 20px;
    border-top-left-radius: 20px;
}
.holder{

    padding-left: 5vw;
    padding-right: 5vw;
    box-sizing: border-box;

    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: auto 1fr  ;
    place-items: center;
    
    height: 100vh;
    width: 100%;
    background-color: var(--light-brown);
    

    color: var(--dark-gray);
}
.being-relative{
    position: relative;
}
.not-being-relative{
    position: relative;
}
.holder header{
    font-size: var(--medieum-text-size);
    padding-top: calc(var(--main-nav-bar-height) + 10px);

    display: flex;
    justify-content: center;
    align-items: center;
    
    color: var(--dark-gray);
    text-decoration: underline;
}
.holder span{
}
.holder p{
    font-size: var(--medieum-text-size);
}
.quote{
    text-align: center;
    width: 75%;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
.quote span{
    font-size: 20px;
}
@media (max-width: 720px) {
    .about-me{
        font-size: var(--medieum-text-size-phone);
        height: var(--main-nav-bar-height-mobile);

    }
    .being-nav{
        top: var(--main-nav-bar-height-mobile);
    }
    .not-being-nav{
        position: absolute;
        left: 50%;
        top:0;
        transform: translateX(-50%);
        z-index: 99999;

        padding-top: calc(var(--main-nav-bar-height-mobile) + 10px);
        
        color: var(--dark-gray);
        text-decoration: underline;
        
        width: 100%;
    }
    .about-me-text{
        font-size: var( --big-text-size-mobile - 5);
    }
    .quote span{
        font-size: 10px;
        width: 100%;
    }

}

@keyframes aboutEntering {
    0%{left: 100%;}
    100%{left: 0%;}
}
</style>