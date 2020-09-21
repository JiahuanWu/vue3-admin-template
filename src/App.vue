<template>
  <aside class="sidebar">
    <Menu />
  </aside>
  <main class="content">
    <router-view />
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Menu from './components/Menu.vue';

export default defineComponent({
  name: 'App',
  components: {
    Menu,
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #081C15;
}
.sidebar {
  width: 20rem;
  line-height: 2;
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  border-right: 1px solid #eee;
  box-shadow: 6px 0 4px -3px #eee;
}
.content {
  padding-left: 20rem;
  padding-bottom: 2rem;
}
</style>
