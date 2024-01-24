<script setup lang="ts">
import { ref } from "vue";
import HelloWorld from './components/HelloWorld.vue'
import TestItem from './components/TestItem.vue'

window.electronAPI.sendMessage('Hello from App.vue!');

interface Item {
  icon: string;
  title: string;
}

const itemList = ref<Item[]>([
    {
        icon: '/vite.svg',
        title: 'Vite logo'
    },
    {
        icon: '/vue.svg',
        title: 'Vue logo'
    },
]);

</script>

<template>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
    <TestItem 
      v-for="(item, index) in itemList"
      :key="item.title"
      :icon="item.icon" 
      :title="item.title" 
    />
  </div>
  <HelloWorld msg="Vite + Vue" />
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
