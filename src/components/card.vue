<script setup >
const props = defineProps({
    socialMedia : String,
    userName : String,
})
</script>
<template>
    <div class="card" >
        <p class="card-social-media" > {{ socialMedia }} </p>
        <p class="card-social-media-username" > {{ userName }}</p>
        <div class="circle" >
            <slot name="socialMediaSVG" ></slot>
        </div>
    </div>
</template>
<style scoped>
.circle{
    --circle-width : 50px;
    height: var(--circle-width);
    width: var(--circle-width);

    background-color: var(--dark-gray);

    border-radius: 50%;
    padding: 15px;
    box-sizing: border-box;

    grid-row: 1/3;
    grid-column: 2/3;
}
.card{
    position: relative;

    display: grid;
    grid-template-columns: 1fr auto;
    grid-template-rows: 1fr 1fr;

    border-top: solid 2px var(--dark-gray);

    box-sizing: border-box;
    padding-top:5px ;

    min-width: 300px;
    transition: all 0.25s ease;
    

    cursor: pointer;
}

.card *{
    z-index: 8;
}
.card:hover > .circle{
    scale: 1.1;
}
.card::before{
    content: "";

    position: absolute;
    left: 0;
    top: -2px;
    width: 100%;
    height: 2px;

    background-color: var(--dark-gray);

    transition: height 0.25s ease;
    z-index: 5;
}

.card:hover::before{
    height: 100%;
}
.card:hover{
    color: var(--light-brown);

    padding: 3px;
    scale: 1.5;

    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);

    z-index: 99;
}
.card-social-media-username{
    grid-row: 2/3;
    grid-column: 1/2;
    
    font-size: 10px;
}
.card-social-media{
    grid-row: 1/2;
    grid-column: 1/2;
    
    font-weight: 200;

    font-size: var(--medieum-text-size);
}
@media (max-width: 720px) {

    .card:hover{

        scale: 1.1;


    }
    
}


</style>