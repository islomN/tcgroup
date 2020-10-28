<template>
  <div class="wrapper">
    <notifications></notifications>
    <tc-side-bar>
      <template slot-scope="props" slot="links">

        <div class="d-flex flex-wrap align-content-between" style="height: calc(100vh - 94px)" >
          <div class="w-100">
            <tc-sidebar-item
              :link="{
                    name: 'Dashboards',
                    icon: {
                      default: 'dashboard-icon',
                      active: 'active-dashboard-icon',
                      base: 'tc-icon menu text-primary'
                    },
                    path: '/'
                  }"
            ></tc-sidebar-item>

            <tc-sidebar-item
              :link="{
                    name: 'Finances',
                    icon: {
                      default: 'finances-icon',
                      active: 'active-finances-icon',
                      base: 'tc-icon menu text-primary'
                    },
                  }"
            >
              <tc-sidebar-item
                :link="{ name: 'Wallet', path: '/finances' }"
              ></tc-sidebar-item>
              <tc-sidebar-item
                :link="{ name: 'Operations history', path: '/finances' }"
              ></tc-sidebar-item>
            </tc-sidebar-item>

            <tc-sidebar-item
              :link="{
                    name: 'Licence',
                    icon: {
                      default: 'license-icon',
                      active: 'active-license-icon',
                      base: 'tc-icon menu text-primary'
                    },
                    path: '/'
                  }"
            ></tc-sidebar-item>

            <tc-sidebar-item
              :link="{
                    name: 'Investments',
                    icon: {
                      default: 'investments-icon',
                      active: 'active-investments-icon',
                      base: 'tc-icon menu text-primary'
                    },
                    path: '/'
                  }"
            ></tc-sidebar-item>

            <tc-sidebar-item
              :link="{
                    name: 'Finances',
                    icon: {
                      default: 'finances-icon',
                      active: 'active-finances-icon',
                      base: 'tc-icon menu text-primary'
                    },
                  }"
            >
              <tc-sidebar-item
                :link="{ name: 'Wallet', path: '/finances' }"
              ></tc-sidebar-item>
              <tc-sidebar-item
                :link="{ name: 'Operations history', path: '/finances' }"
              ></tc-sidebar-item>
            </tc-sidebar-item>

            <tc-sidebar-item
              :link="{
                    name: 'Finances',
                    icon: {
                      default: 'finances-icon',
                      active: 'active-finances-icon',
                      base: 'tc-icon menu text-primary'
                    },
                  }"
            >
              <tc-sidebar-item
                :link="{ name: 'Wallet', path: '/finances' }"
              ></tc-sidebar-item>
              <tc-sidebar-item
                :link="{ name: 'Operations history', path: '/finances' }"
              ></tc-sidebar-item>
            </tc-sidebar-item>

            <tc-sidebar-item
              :link="{
                    name: 'Documents',
                    icon: {
                      default: 'document-icon',
                      active: 'active-document-icon',
                      base: 'tc-icon menu text-primary'
                    },
                    path: '/'
                  }"
            ></tc-sidebar-item>
          </div>

          <div class="social-links w-100">
            <span class="tc-icon telegram-icon"></span>
            <span class="tc-icon instagram-icon"></span>
            <span class="tc-icon facebook-icon"></span>
          </div>

        </div>
      </template>
    </tc-side-bar>
    <div class="main-content">
      <tc-dashboard-navbar :type="$route.name === 'alternative' ? 'light': 'default'"></tc-dashboard-navbar>

      <div @click="$sidebar.displaySidebar(false)">
        <nuxt></nuxt>
      </div>
      <content-footer v-if="!$route.meta.hideFooter"></content-footer>
    </div>
  </div>
</template>
<script>
/* eslint-disable no-new */
import PerfectScrollbar from 'perfect-scrollbar';
import 'perfect-scrollbar/css/perfect-scrollbar.css';

function hasElement(className) {
  return document.getElementsByClassName(className).length > 0;
}

function initScrollbar(className) {
  if (hasElement(className)) {
    new PerfectScrollbar(`.${className}`);
  } else {
    // try to init it later in case this component is loaded async
    setTimeout(() => {
      initScrollbar(className);
    }, 100);
  }
}

import DashboardNavbar from '~/components/layouts/argon/DashboardNavbar.vue';
import ContentFooter from '~/components/layouts/argon/ContentFooter.vue';
import DashboardContent from '~/components/layouts/argon/Content.vue';
import TcSideBar from "~/components/layouts/tc/TcSideBar";
import TcSidebarItem from "~/components/layouts/tc/TcSidebarItem";
import TcDashboardNavbar from "@/components/layouts/tc/TcDashboardNavbar";
export default {
  components: {
    DashboardNavbar,
    ContentFooter,
    DashboardContent,
    TcSideBar,
    TcSidebarItem,
    TcDashboardNavbar
  },
  methods: {
    initScrollbar() {
      let isWindows = navigator.platform.startsWith('Win');
      if (isWindows) {
        initScrollbar('scrollbar-inner');
      }
    }
  },
  mounted() {
    this.initScrollbar()
  }
};
</script>
<style lang="scss">
</style>

<style>
body{
  background: #F8F8F8;
}
.tc-icon.menu{
  width: 30px;
  height: 30px;
  zoom: .7;
  margin-right: 12px;
}
.social-links{
  display: flex;
  flex-wrap: wrap;
  padding: 20px;
  padding-bottom: 0;
  justify-content: space-around;
  width: 100%;
}
.social-links span.tc-icon{
  width: 25px;
  height: 25px;
  cursor: pointer;
  justify-content: center;
}
.sidenav-header.d-flex.align-items-center{
  border-bottom: 1px solid #ddd;
}
</style>
