<script setup>
import sectionComponent from "../components/section.vue"
import card from "@/components/card.vue";

import linkedIN from "@/assets/images/icons/LinkedIn.png"
import emailMe from "@/assets/images/icons/mail.png"
</script>

<template>
      <sectionComponent
      id="contact"
    header="Hit me up!"
    :index="3">


    <template #content >

      <div class="holder-contact">
        <!-- linked in -->
        <card 
        :socialMedia="'Linked in'"
        :userName="'@belhanafi_abdelmadjid'"
        >
            <template #socialMediaSVG >
                <img :src="linkedIN" alt="">
            </template>
        </card>
        
        <!-- email -->
        <card
        :socialMedia="'Email me'"
        :userName="'belhanafiabdelmadjid@gmail.com'"
        >
            <template #socialMediaSVG >
                <img :src="emailMe" alt="">
            </template>
        </card>
        
        <!-- facebook -->
        <card
        :socialMedia="'Facebook'"
        :userName="'@Belhanafi Abdelmadjid'"
        >
            <template #socialMediaSVG >
                <svg width="100%" height="100%" viewBox="0 0 19 19" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M17.9486 0C18.2372 0 18.4846 0.103082 18.6908 0.309245C18.8969 0.515408 19 0.762804 19 1.05143V17.9486C19 18.2372 18.8969 18.4846 18.6908 18.6908C18.4846 18.8969 18.2372 19 17.9486 19H13.112V11.64H15.5736L15.9447 8.77018H13.112V6.93945C13.112 6.47765 13.2089 6.13129 13.4027 5.90039C13.5965 5.66949 13.9737 5.55404 14.5345 5.55404L16.0436 5.54167V2.98112C15.5241 2.9069 14.7901 2.86979 13.8418 2.86979C12.7203 2.86979 11.8235 3.19965 11.1514 3.85938C10.4793 4.5191 10.1432 5.45095 10.1432 6.65495V8.77018H7.66927V11.64H10.1432V19H1.05143C0.762804 19 0.515408 18.8969 0.309245 18.6908C0.103082 18.4846 0 18.2372 0 17.9486V1.05143C0 0.762804 0.103082 0.515408 0.309245 0.309245C0.515408 0.103082 0.762804 0 1.05143 0H17.9486Z" fill="#F3F3F3"/>
                </svg>

            </template>
        </card>

      </div>
    </template>

  </sectionComponent>
</template>

<style scoped>
.holder-contact{

    display: flex;
    justify-content: space-evenly;
    align-items: center;

    width: 100%;
}
.circle img{
    height: auto;
    width: 100%;
}
@media (max-width: 1300px) {
    .holder-contact{
        flex-direction: column;
        justify-content: space-around;

        height: 100%;
    }

}


</style>