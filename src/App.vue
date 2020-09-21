<template>
  <Menu />
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
</style>
