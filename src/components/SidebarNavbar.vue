<template>
  <div class="sidebar" :style="{ width: sidebarWidth }">
    <h1>
      <span v-if="collapsed">
        <div>V</div>
        <div>S</div>
      </span>
      <span v-else>Vue Sidebar</span>
    </h1>

    <SidebarLink to="/" icon="fa fa-home" class="pad-class"> Home </SidebarLink>
    <SidebarLink to="/dashboard" icon="fa fa-columns" class="pad-class">
      Dashboard
    </SidebarLink>
    <SidebarLink to="/analytics" icon="fa fa-bar-chart" class="pad-class">
      Analytics
    </SidebarLink>
    <SidebarLink to="/Contacts" icon="fa fa-user" class="pad-class">
      Contacts
    </SidebarLink>
    <SidebarLink to="/settings" icon="fa fa-cog" class="pad-class">
      Settings
    </SidebarLink>
    <span
      class="collapsed-icon"
      :class="{ 'rotate-180': collapsed }"
      @click="toggleSidebar"
    >
      <i class="fa fa-angle-double-left fa-lg" aria-hidden="true"></i>
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
  /* --sidebar-bg-color: #2f855a; */
  --sidebar-item-hover: #38a169;
  --sidebar-item-active: #276749;
}
</style>

<style scoped>
.pad-class {
  padding-right: 21px;
}
.sidebar {
  color: rgb(255, 255, 255);
  background: linear-gradient(0.25turn, #212121, #066d20, #212121);

  float: right;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  margin-right: 10px;
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
  transition: 0.5s linear;
}
</style>
