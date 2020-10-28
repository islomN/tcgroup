<template>
  <base-dropdown menu-on-right
                 class="nav-item"
                 tag="li"
                 title-tag="a"
                 title-classes="nav-link pr-0">
    <a href="#" class="nav-link pr-0" @click.prevent slot="title-container">
      <div class="media align-items-center">
                  <span class="avatar avatar-sm rounded-circle">
                    <img alt="Image placeholder" src="img/theme/team-4.jpg">
                  </span>
        <div class="media-body ml-2 d-none d-lg-block">
          <span class="mb-0 text-sm  font-weight-bold">John Snow</span>
        </div>
      </div>
    </a>

    <template>
      <div class="dropdown-header noti-title">
        <h6 class="text-overflow m-0">Welcome!</h6>
      </div>
      <a href="#!" class="dropdown-item">
        <i class="ni ni-single-02"></i>
        <span>My profile</span>
      </a>
      <a href="#!" class="dropdown-item">
        <i class="ni ni-settings-gear-65"></i>
        <span>Settings</span>
      </a>
      <a href="#!" class="dropdown-item">
        <i class="ni ni-calendar-grid-58"></i>
        <span>Activity</span>
      </a>
      <a href="#!" class="dropdown-item">
        <i class="ni ni-support-16"></i>
        <span>Support</span>
      </a>
      <div class="dropdown-divider"></div>
      <a href="#!" class="dropdown-item">
        <i class="ni ni-user-run"></i>
        <span>Logout</span>
      </a>

    </template>
  </base-dropdown>
</template>

<script>
export default {
  name: "TcProfile"
}
</script>

<style scoped>

</style>
