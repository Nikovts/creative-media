<template>
  <div class="main">
    <header>
      <h1 class="title">We make creative media that <span>adds value</span></h1>
    </header>
    <section>
      <Card v-for="item,i in data" :key="i" :item="item"/>
    </section>
    <footer>
      <span>Get STARTED</span>
    </footer>
  </div>
</template>

<script setup>
import Card from "./Card.vue";
import { ref } from 'vue'
import dataDB from "../assets/data.json";

const data = ref(dataDB)
</script>

<style lang="scss" scoped>
.main {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 6.75rem 5.26rem;
}

header {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  width: 45.62rem;
  height: 6.875rem;
}

section {
  margin: 5rem 0;
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 2.5rem 1.875rem;
}

footer {
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  padding: 0px 3.625rem;
  width: 19.69rem;
  height: 3.75rem;
  background: #1B264F;
  border-radius: 0.75rem;

  span {
    font-weight: 700;
    font-size: 1.0625rem;
    line-height: 3.75rem;
    text-align: center;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: #FFFFFF;
    cursor: pointer;
  }
}
.title{
  font-style: normal;
  font-weight: 700;
  font-size: 3.5rem;
  line-height: 98%;

  text-align: center;
  letter-spacing: -0.01em;

  color: #1B264F;

  span {
    font-style: normal;
    font-weight: 700;
    font-size: 3.5rem;
    line-height: 98%;
    color:#506BCA;
  }
}

</style>