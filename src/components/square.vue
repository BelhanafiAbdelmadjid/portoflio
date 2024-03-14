<script setup >
import { ref, onMounted } from 'vue'
const props = defineProps({
    ImageName : String
})
</script>
<template>
    <div class="square" >
        <slot name="image" ></slot>
    </div>
</template>
<style scoped>




.square{
    --square-size : 150px;
    height: var(--square-size);
    width: var(--square-size);

    border-radius: 10px;

    background-color: var(--dark-gray);

    animation: floatAnimation 2s infinite ease-in-out; /* Adjust duration and timing function as needed */

    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);

    animation: floatAnimation 1s infinite alternate ease-in-out; /* Adjust duration and timing function */
}


@keyframes floatAnimation {
  0% {
    transform: translateY(0);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
  }

  100% {
    transform: translateY(-30px); /* Adjust the vertical distance for the floating effect */
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.5); /* Adjust shadow size for the floating effect */
  }
}
@media (max-width: 720px) {
.square{
    display: flex;
    justify-content: center;
    align-items: center;

    --square-size : 100px;
}

}
</style>