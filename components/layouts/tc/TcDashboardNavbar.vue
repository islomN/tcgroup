<template>
  <base-nav
    container-classes="container-fluid"
    class="navbar-top border-bottom navbar-expand p-0"
  >
    <!-- Navbar links -->
    <ul class="navbar-nav align-items-center justify-content-between w-100">
      <tc-language main-class="left"></tc-language>
      <div class="d-flex align-items-center">
        <tc-licence-info main-class="nav-item"></tc-licence-info>
        <tc-balance-info main-class="nav-item "></tc-balance-info>
        <!--    </ul>-->
        <!--    <ul class="navbar-nav align-items-center ml-auto ml-md-0 border-left">-->
        <tc-notification-section></tc-notification-section>
        <tc-profile></tc-profile>
      </div>
    </ul>
  </base-nav>
</template>
<script>
import { CollapseTransition } from 'vue2-transitions';
import TcLanguage from "@/components/layouts/tc/partial/TcLanguage";
import TcNotificationSection from "@/components/layouts/tc/partial/TcNotificationSection";
import TcProfile from "@/components/layouts/tc/partial/TcProfile";
import TcLicenceInfo from "@/components/layouts/tc/partial/TcLicenceInfo";
import TcBalanceInfo from "@/components/layouts/tc/partial/TcBalanceInfo";
export default {
  components: {
    CollapseTransition,
    TcLanguage,
    TcNotificationSection,
    TcProfile,
    TcBalanceInfo,
    TcLicenceInfo
  },
  props: {
    type: {
      type: String,
      default: 'default', // default|light
      description: 'Look of the dashboard navbar. Default (Green) or light (gray)'
    }
  },
  computed: {
    routeName() {
      const { name } = this.$route;
      return this.capitalizeFirstLetter(name);
    }
  },
  data() {
    return {
      activeNotifications: false,
      showMenu: false,
      searchModalVisible: false,
      searchQuery: ''
    };
  },
  methods: {
    capitalizeFirstLetter(string) {
      return string.charAt(0).toUpperCase() + string.slice(1);
    },
    toggleNotificationDropDown() {
      this.activeNotifications = !this.activeNotifications;
    },
    closeDropDown() {
      this.activeNotifications = false;
    },
    toggleSidebar() {
      this.$sidebar.displaySidebar(!this.$sidebar.showSidebar);
    },
    hideSidebar() {
      this.$sidebar.displaySidebar(false);
    }
  }
};
</script>
