<template>
  <div class="sidebar">
    <div class="top-row pl-4 navbar navbar-dark">
      <a class="navbar-brand" href="">Asp.Net Core/Vue Starter</a>
      <button class="navbar-toggler" @click="ToggleNavMenu">
        <span class="navbar-toggler-icon"></span>
      </button>
    </div>
    <div :class="{ collapse: collapseNavMenu }" @click="ToggleNavMenu">
      <ul class="nav flex-column">
        <li class="nav-item px-3" v-for="(item, i) in items" :key="i">
          <router-link class="nav-link" :to="item.link" exact>
            <span :class="item.icon" aria-hidden="true"></span> {{ item.title }}
          </router-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

@Component
export default class NavMenu extends Vue {
  private collapseNavMenu = false
  private items = [
    { title: 'Home', icon: 'oi oi-home', link: '/' },
    { title: 'Counter', icon: 'oi oi-plus', link: '/counter' },
    { title: 'Fetch data', icon: 'oi oi-list-rich', link: '/fetch-data' }
  ]

  ToggleNavMenu(): void {
    this.collapseNavMenu = !this.collapseNavMenu
  }
}
</script>

<style scoped>
.navbar-toggler {
  background-color: rgba(255, 255, 255, 0.1);
}

.top-row {
  height: 3.5rem;
  background-color: rgba(0, 0, 0, 0.4);
}

.navbar-brand {
  font-size: 1.1rem;
}

.oi {
  width: 2rem;
  font-size: 1.1rem;
  vertical-align: text-top;
  top: -2px;
}

.nav-item {
  font-size: 0.9rem;
  padding-bottom: 0.5rem;
}

.nav-item:first-of-type {
  padding-top: 1rem;
}

.nav-item:last-of-type {
  padding-bottom: 1rem;
}

.nav-item ::v-deep a {
  color: #d7d7d7;
  border-radius: 4px;
  height: 3rem;
  display: flex;
  align-items: center;
  line-height: 3rem;
}

.nav-item ::v-deep a.router-link-active {
  background-color: rgba(255, 255, 255, 0.25);
  color: white;
}

.nav-item ::v-deep a:hover {
  background-color: rgba(255, 255, 255, 0.1);
  color: white;
}

@media (min-width: 641px) {
  .navbar-toggler {
    display: none;
  }

  .collapse {
    /* Never collapse the sidebar for wide screens */
    display: block !important;
  }
}
</style>
