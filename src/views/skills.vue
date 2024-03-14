<script setup>
import sectionComponent from "../components/section.vue";
import squareComponent from "../components/square.vue";

import CPNG from "@/assets/images/skills/c.png"
import JSPNG from "@/assets/images/skills/js.png"
import DOCKERPNG from "@/assets/images/skills/docker.png"
import flaskPNG from "@/assets/images/skills/flask.jpg"
import HtmlCssPNG from "@/assets/images/skills/HtmlCss.png"
import javaPNG from "@/assets/images/skills/java.png"
import kaliPNG from "@/assets/images/skills/kali.jpg"
import mysqlPNG from "@/assets/images/skills/mysql.png"
import pythonPNG from "@/assets/images/skills/python.png"
import threePNG from "@/assets/images/skills/three.png"
import vuePNGPNG from "@/assets/images/skills/vue.png"
import LaravelPNG from "@/assets/images/skills/Laravel.png"
</script>

<template>
  <sectionComponent header="Skills" :index="2">
    <template #content >
      <div class="holder-skills" >
        <div class="line1">
          <squareComponent>
          <template #image>
            <img :src="LaravelPNG" alt="C Langauge.">
          </template>
        </squareComponent>
          <squareComponent>
          <template #image>
            <img :src="vuePNGPNG" alt="C Langauge.">
          </template>
        </squareComponent>
          <squareComponent>
          <template #image>
            <img :src="threePNG" alt="C Langauge.">
          </template>
        </squareComponent>
          <squareComponent>
          <template #image>
            <img :src="pythonPNG" alt="C Langauge.">
          </template>
        </squareComponent>
          <squareComponent>
          <template #image>
            <img :src="CPNG" alt="C Langauge.">
          </template>
        </squareComponent>
        <squareComponent  >
          <template #image>
            <img :src="JSPNG" alt="JS Langauge.">
          </template>
        </squareComponent>
        

        </div>
        <div class="line1-replicat">
          <squareComponent>
          <template #image>
            <img :src="LaravelPNG" alt="C Langauge.">
          </template>
        </squareComponent>
          <squareComponent>
          <template #image>
            <img :src="vuePNGPNG" alt="C Langauge.">
          </template>
        </squareComponent>
          <squareComponent>
          <template #image>
            <img :src="threePNG" alt="C Langauge.">
          </template>
        </squareComponent>
          <squareComponent>
          <template #image>
            <img :src="pythonPNG" alt="C Langauge.">
          </template>
        </squareComponent>
          <squareComponent>
          <template #image>
            <img :src="CPNG" alt="C Langauge.">
          </template>
        </squareComponent>
        <squareComponent  >
          <template #image>
            <img :src="JSPNG" alt="JS Langauge.">
          </template>
        </squareComponent>
        

        </div>
        <div class="line2">
          <squareComponent >
          <template #image>
            <img :src="DOCKERPNG" alt="C Langauge.">
          </template>
        </squareComponent>
        <squareComponent  >
          <template #image>
            <img :src="flaskPNG" alt="C Langauge.">
          </template>
        </squareComponent>
        <squareComponent  >
          <template #image>
            <img :src="HtmlCssPNG" alt="C Langauge.">
          </template>
        </squareComponent>
        <squareComponent  >
          <template #image>
            <img :src="javaPNG" alt="C Langauge.">
          </template>
        </squareComponent>
        <squareComponent  >
          <template #image>
            <img :src="kaliPNG" alt="C Langauge.">
          </template>
        </squareComponent>
        <squareComponent  >
          <template #image>
            <img :src="mysqlPNG" alt="C Langauge.">
          </template>
        </squareComponent>
        </div>
        <div class="line2-replicat">
          <squareComponent >
          <template #image>
            <img :src="DOCKERPNG" alt="C Langauge.">
          </template>
        </squareComponent>
        <squareComponent  >
          <template #image>
            <img :src="flaskPNG" alt="C Langauge.">
          </template>
        </squareComponent>
        <squareComponent  >
          <template #image>
            <img :src="HtmlCssPNG" alt="C Langauge.">
          </template>
        </squareComponent>
        <squareComponent  >
          <template #image>
            <img :src="javaPNG" alt="C Langauge.">
          </template>
        </squareComponent>
        <squareComponent  >
          <template #image>
            <img :src="kaliPNG" alt="C Langauge.">
          </template>
        </squareComponent>
        <squareComponent  >
          <template #image>
            <img :src="mysqlPNG" alt="C Langauge.">
          </template>
        </squareComponent>
        </div>
        
      </div>
    </template>
  </sectionComponent>
</template>

<style scoped>
.holder-skills{
  position: absolute;
  height: 50%;
  width:100vw;


  padding: 2%;
  
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  gap: 10px;


  box-sizing: border-box;

  z-index: 0;
  
}
.holder-skills .line1, .holder-skills .line2 , .line2-replicat , .line1-replicat{
  position: absolute;
  width: 200%;

  display: flex;
  justify-content: space-between;
  align-items: center;

  animation: slideAnimation 15s linear infinite; /* Adjust duration and timing function as needed */
}
.holder-skills .line1{
  transform: translateX(25%);
  animation-direction: normal;

  bottom:0;
}
.holder-skills .line2{
  animation-direction: reverse;
  top:0;
}
.line2-replicat{
  animation: slideAnimation 15s linear infinite;
  animation-direction: reverse;
  left: calc(150% + 25vw);
  top:0;
}
.line1-replicat{
  animation: slideAnimation 15s linear infinite;
  left: calc(150% + 25vw);
  bottom:0;
}

.holder-skills img{
  width: 100%;
  height: auto;
}

@media (max-width: 720px) {

  .holder-skills{
    gap: 0px;
}

.holder-skills .line1, .holder-skills .line2 , .line2-replicat , .line1-replicat{
  width: 300%;
}

}

@keyframes slideAnimation {
  0% {
    transform: translateX(0%);
  }

  100% {
    transform: translateX(-100%);
  }
}

</style>
