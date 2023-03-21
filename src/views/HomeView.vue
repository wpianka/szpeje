<script>
import HeaderPage from '@/components/HeaderPage.vue'
import szpej from '@/data/szpej.json'
import { findDir } from '@vue/compiler-core';
const zmienna = szpej;
console.log(zmienna);

  export default{
    data(){
      return{
        wybieranie: 'wybierz'
      }
    },

    methods: {
      formSumbit(){
        zmienna.forEach(element => {
          if(element.category.find(c => c == this.wybieranie) == this.wybieranie){
            console.log(element.name);
          }
        });
      }
    }
  };


</script>

<template>
  <HeaderPage />
  <main>
    <h1>Home Page</h1>

    <form v-on:submit.prevent="formSumbit">
      <select v-model="wybieranie">
        <option disabled value="">Wybierz</option>
        <option>mountains</option>
        <option>bicycle</option>
        <option>skitour</option>
      </select>

      <dir>{{ wybieranie }}</dir>

      <button type="submit">Wyślij</button>
    </form>
  </main>
</template>
