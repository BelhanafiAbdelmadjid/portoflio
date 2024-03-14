<script setup>
defineProps({

})
import mePicture from "@/assets/images/portfolio.jpg"
</script>

<template>

  <div   class="holder" >
    <p>
      A full stack web developer from Algeria, here to craft simple and useful experiences. 
    </p>
    <img :src="mePicture"  alt="">
  </div>

</template>

<style scoped>
.holder{
  height: 100%;
  width: 100%;
  
  letter-spacing: -2%;

  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;

  box-sizing: border-box;

}
.holder img{
  width: 25%;
  filter: grayscale(0.5);

  border-radius: 50%;
}
.holder p{
  font-size: var(--big-text-size);
  margin: auto;
  transition: 
  font-size 0.25s ease;
  box-sizing: border-box;
}

@media (max-width: 720px) {
  .holder p{
    font-size: var(--big-text-size-mobile);
  }
  .holder{
    align-items: center;
  }

}
</style>
