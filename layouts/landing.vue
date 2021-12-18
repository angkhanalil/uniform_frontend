<template>
  <div class="content">
    <!-- Topbar Start -->
    <div class="navbar-custom" style="position: initial">
      <ul class="list-unstyled topbar-menu float-end mb-0">
        <li class="dropdown notification-list d-lg-none">
          <a
            class="nav-link dropdown-toggle arrow-none"
            data-bs-toggle="dropdown"
            href="#"
            role="button"
            aria-haspopup="false"
            aria-expanded="false"
          >
            <i class="dripicons-search noti-icon"></i>
          </a>
          <div class="dropdown-menu dropdown-menu-animated dropdown-lg p-0">
            <form class="p-3">
              <input
                type="text"
                class="form-control"
                placeholder="Search ..."
                aria-label="Recipient's username"
              />
            </form>
          </div>
        </li>
      </ul>
    </div>
    <div class="container-fluid">
      <Nuxt />
    </div>
  </div>
</template>

<script> 
export default { 
} 
</script>

<style>
</style>