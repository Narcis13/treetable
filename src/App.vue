<script setup>
import HelloWorld from './components/HelloWorld.vue'
const people=[
          { name: 'Alice', age: 25, gender: 'female' },
          {name:'Narcis',age:99,gender:'male'},
          { name: 'Bob', age: 30, gender: 'male' },
          { name: 'Charlie', age: 20, gender: 'male' },
          { name: 'Danielle', age: 35, gender: 'female'}]
</script>

<template>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <hello-world :data="people" group-by="gender"></hello-world>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
