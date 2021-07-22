<template>
  <div class="sidebar" :style="{ width: sidebarWidth }">
    <h1>
      <span v-if="collapsed">
        <div>V</div>
        <div>S</div>
      </span>
      <span v-else>Vue Sidebar</span>
    </h1>

    <SidebarLink to="/">
      <i class="fa fa-home" aria-hidden="true"></i> Home
    </SidebarLink>
    <SidebarLink to="/dashboard">
      <i class="fa fa-columns" aria-hidden="true"></i> Dashboard
    </SidebarLink>
    <SidebarLink to="/analytics">
      <i class="fa fa-bar-chart" aria-hidden="true"></i>
      Analytics
    </SidebarLink>
    <SidebarLink to="/Contacts">
      <i class="fa fa-user" aria-hidden="true"></i> Contacts
    </SidebarLink>
    <SidebarLink to="/settings">
      <i class="fa fa-cog" aria-hidden="true"></i> Settings
    </SidebarLink>
    <span
      class="collapsed-icon"
      :class="{ 'rotate-180': collapsed }"
      @click="toggleSidebar"
    >
      <i class="fa fa-angle-double-left" aria-hidden="true"></i>
    </span>
  </div>
</template>

<script>
import SidebarLink from '../components/SidebarLink.vue'
import { collapsed, toggleSidebar, sidebarWidth } from './state'
export default {
  props: {},
  components: { SidebarLink },
  name: 'SidebarNavbar',
  setup() {
    return {
      collapsed,
      toggleSidebar,
      sidebarWidth
    }
  }
}
</script>

<style>
:root {
  --sidebar-bg-color: #2f855a;
  --sidebar-item-hover: #38a169;
  --sidebar-item-active: #276749;
}
</style>

<style scoped>
.sidebar {
  color: white;
  background-color: var(--sidebar-bg-color);

  float: left;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  bottom: 0;
  padding: 0.5em;

  transition: 0.3s ease;

  display: flex;
  flex-direction: column;
}

.collapse-icon {
  position: absolute;
  bottom: 0;
  padding: 0.75em;
  transform: scale(1);
  color: rgba(255, 255, 255, 0.7);
  transition: 0.2s linear all;
}

.rotate-180 {
  transform: scale(-1);
  transition: 0.2s linear;
}
</style>
