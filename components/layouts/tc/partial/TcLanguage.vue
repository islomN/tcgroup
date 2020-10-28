<template>
  <li
    :class="[{ show: isOpen }, 'dropdown language-main-section', mainClass]"
    @click="toggleDropDown"
    v-click-outside="closeDropDown"
  >
    <a data-toggle="dropdown" class="btn-rotate nav-link language-wrapper" :aria-expanded="isOpen">
      <div class="language-active">
        <span class="flag tc-icon usa-icon"></span>
        <span class="name">English</span>
        <span class="down tc-icon down-icon"></span>
      </div>
    </a>
    <ul class="dropdown-menu py-0 overflow-hidden"
        :class="[
        { show: isOpen },
        'overflow-hidden'
      ]">
      <div class="position-relative language-list">
        <a  href="#!" class="dropdown-item">
          <span class="flag tc-icon usa-icon"></span>
          <span class="name">English</span>
        </a>
        <a href="#!" class="dropdown-item">
          <span  class="flag tc-icon usa-icon"></span>
          <span  class="name">Russian</span>
        </a>
      </div>
    </ul>
  </li>
</template>

<script>
export default {
  name: "TcLanguage",
  props:{
    mainClass:{
      type: String,
      default: 'nav-link'
    },
    icon:{

    }
  },
  data() {
    return {
      isOpen: false
    };
  },
  methods: {
    toggleDropDown() {
      this.isOpen = !this.isOpen;
      this.$emit('change', this.isOpen);
    },
    closeDropDown() {
      this.isOpen = false;
      this.$emit('change', false);
    }
  }
}
</script>

<style scoped>
.flag.tc-icon{
  width: 20px;
  height: 20px;
  position: absolute;
  left: 0;
  top: 7px;
}
.language-list a span{
  display: inline;
}

.language-list a span.name{
  width: calc(100%-30px);
  margin-left: 30px;
}
.language-main-section{
  min-width: 150px;
}
.language-wrapper {
  padding-left: 25px !important;
}
</style>
