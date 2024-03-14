<script setup>
import sectionComponent from "../components/section.vue"
</script>

<template>
      <sectionComponent
      id="intro"
      class="animate"
  header="About me"
  :index="1">


    <template #content >

      <div class="holder-about">
        <p class="about-me-text" >
            My passion for web dev is increasing with every new project 
            i’m implicated in, because of my limitless creativity since i
            entered the IT world creating and crafting new stuff was a hobbie for me,
            if you like facing new challenges i’d really apreaciate to collaborate with 
            you and turn your ideas into successfull story you’d be proud of.
        </p>
        <p class="quote" >
            <i><storng>
                “It is our attitude at the beginning of a difficult task which,
                more than anything else, will affect its successful outcome.”
            </storng></i>
            <span>
                – William James
            </span>
        </p>
      </div>
    </template>

  </sectionComponent>
</template>

<style scoped>


.animate {
  box-shadow: 0px 0px 10px 5px rgba(0, 0, 0, 0.3);
  animation: moveShadow 2s infinite alternate;
}

@keyframes moveShadow {
  0% {
    box-shadow: 0px 0px 10px 5px rgba(0, 0, 0, 0.3);
  }
  100% {
    box-shadow: 10px 10px 20px 10px rgba(0, 0, 0, 0.3);
  }
}

.holder-about{


    display:flex;
    flex-direction : column;
    justify-content: space-evenly;
    align-items:center;
    
    height: 100%;
}

.holder-about p{
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


    .quote span{
        font-size: 10px;
        width: 100%;
    }
    .quote i{
        font-size: 14px;
    }
    .holder-about p{
        font-size: 20px;
    }

}


</style>