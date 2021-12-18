<template>
  <!-- Begin page -->
  <div class="wrapper">
    <!-- ========== Left Sidebar Start ========== -->
    <Sidebar />
    <div class="content-page">
      <div class="content">
        <!-- Topbar Start -->
        <Navbar />
        <div class="container-fluid">
          <Nuxt />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Sidebar from '~/components/sidebar.vue'
import Navbar from '~/components/navbar.vue'
export default {
  components: {
    Sidebar,
    Navbar,
  },
  head() {
    return {
      bodyAttrs: {
        class: 'loading',
        'data-layout-config':
          '{"leftSideBarTheme":"dark", "showRightSidebarOnStart": true}',
        'data-leftbar-theme': 'dark',
      },
    }
  },
}
</script>

<style>
body[data-leftbar-theme='dark'] .leftside-menu {
  background: #313a46;
}
</style>