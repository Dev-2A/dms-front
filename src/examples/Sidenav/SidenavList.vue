<template>
  <div
    class="collapse navbar-collapse w-auto h-auto h-100"
    id="sidenav-collapse-main"
  >
    <ul class="navbar-nav">
      <li class="nav-item">
        <sidenav-item
          url="/dashboard-default"
          :class="getRoute() === 'dashboard-default' ? 'active' : ''"
          navText="DashBoard"
        >
          <template v-slot:icon>
            <i class="mdi mdi-car-emergency text-lg text-success"></i>
          </template>
        </sidenav-item>
      </li>
      <li class="nav-item">
        <sidenav-item
          url="/tables"
          :class="getRoute() === 'tables' ? 'active' : ''"
          navText="Shelter Information"
        >
          <template v-slot:icon>
            <i
              class="mdi mdi-coffee text-lg text-success"
            ></i>
          </template>
        </sidenav-item>
      </li>
      <!-- <li class="navbar-item">
        <sidenav-item
          url="/gallery"
          :class="getRoute() === 'gallery' ? 'active' : ''"
          navText="Gallery"
        >
          <template v-slot:icon>
            <i
              class="mdi mdi-panorama text-lg text-success"
            ></i>
          </template>
        </sidenav-item>
      </li> -->
      <li class="mt-3 nav-item">
        <h6 class="text-xs ps-4 text-uppercase font-weight-bolder opacity-6">
          ACCOUNT PAGES
        </h6>
      </li>
      <li class="nav-item">
        <sidenav-item
          url="/profile"
          :class="getRoute() === 'profile' ? 'active' : ''"
          navText="Profile"
        >
          <template v-slot:icon>
            <i class="mdi mdi-account text-lg text-success"></i>
          </template>
        </sidenav-item>
      </li>
      <li class="nav-item">
        <sidenav-item
          url="/signin"
          :class="getRoute() === 'signin' ? 'active' : ''"
          navText="Sign In">
          <template v-slot:icon>
            <i class="mdi mdi-login-variant text-lg text-success"></i>
          </template>
        </sidenav-item>
      </li>
      <li class="nav-item">
        <sidenav-item
          url="/signup"
          :class="getRoute() === 'signup' ? 'active' : ''"
          navText="Sign Up">
          <template v-slot:icon>
            <i class="mdi mdi-account-plus text-lg text-success"></i>
          </template>
        </sidenav-item>
      </li>
    </ul>
  </div>
</template>
<script>
import SidenavItem from "./SidenavItem.vue";

export default {
  name: "SidenavList",
  props: {
    cardBg: String
  },
  data() {
    return {
      title: "Argon Dashboard 2",
      controls: "dashboardsExamples",
      isActive: "active"
    };
  },
  components: {
    SidenavItem,
  },
  methods: {
    getRoute() {
      const routeArr = this.$route.path.split("/");
      return routeArr[1];
    }
  }
};
</script>
