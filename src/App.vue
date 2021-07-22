<template>
  <header>
    <SidebarNavbar />
  </header>
  <main :style="{ 'margin-left': sidebarWidth }">
    <router-view />
  </main>
  <!-- <footer>
    <div class="bg-dark text-light text-center p-4">
      Made with 💖 by CodeWorks
    </div>
  </footer> -->
</template>

<script>
import SidebarNavbar from './components/SidebarNavbar.vue'
import { sidebarWidth } from './components/state'
export default {
  components: { SidebarNavbar },
  name: 'App',
  setup() {
    return {
      sidebarWidth

    }
  }
}
</script>
<style lang="scss">
@import "./assets/scss/main.scss";
</style>
