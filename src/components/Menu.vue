<template>
  <nav class="nav">
    <ul class="nav-ul">
      <li
        v-for="(menu, i) in menus"
        :key="i"
      >
        <a
          :href="menu.href"
          class="menu-link"
          @click="toggle(i)"
        >
          {{ menu.name }}
          <i
            v-if="menu.children && menu.children.length > 0"
            :class="['icon-arrow', menu.isOpen ? 'icon-arrow--down' : 'icon-arrow--up']"></i>
        </a>
        <ul
          v-if="menu.isOpen"
          class="nav-ul"
        >
          <li
            v-for="(subMenu, j) in menu.children"
            :key="j"
          >
            <a
              :href="subMenu.href"
              class="submenu-link"
            >{{ subMenu.name }}</a>
          </li>
        </ul>
      </li>
    </ul>
  </nav>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Menu',
  data() {
    return {
      menus: [
        {
          name: 'New Features',
          children: [
            {
              name: 'Composition API',
              href: '',
            },
          ],
        },
        {
          name: 'Breaking Changes',
          isOpen: false,
        },
      ],
    };
  },
  methods: {
    toggle(i: number) {
      this.menus[i].isOpen = !this.menus[i].isOpen;
    },
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.nav {
  width: 280px;
  line-height: 2;
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  padding-right: 15px;
  border-right: 1px solid #eee;
  box-shadow: 6px 0 4px -3px #eee;
}
.nav-ul {
  list-style: none;
}
.nav a {
  color: #081C15;
  text-decoration: none;
  cursor: pointer;
}
.nav a:hover, .nav a:focus {
  color: #40916C;
}
.menu-link {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 1.25rem;
  font-weight: 700;
}
.icon-arrow {
  border: solid #081C15;
  border-width: 0 2px 2px 0;
  display: inline-block;
  padding: 3px;
}
.icon-arrow--down {
  transform: rotate(45deg);
}

.icon-arrow--up {
  transform: rotate(-135deg);
}
</style>
