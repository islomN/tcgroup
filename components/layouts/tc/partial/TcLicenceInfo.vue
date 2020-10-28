<template>
  <li :class="mainClass">
    <div class="licence-wrapper">
      <div class="d-flex justify-content-between align-items-center">
        <p>
          <span>LICENCE</span>
          FREE
        </p>
        <span class="info tc-icon info-icon"></span>
      </div>
    </div>
  </li>
</template>

<script>
export default {
  name: "TcLicenceInfo",
  props:{
    mainClass:{
      type: String,
      default: ''
    }
  }
}
</script>

<style scoped>
.licence-wrapper {
  padding: 20px 30px;
  border-left: 1px solid #e9ecef;
  border-right: 1px solid #e9ecef;
}
.licence-wrapper span {
  display: block;
  font-size: 10px;
  font-weight: 400;
  line-height: 14px;
  color: #26262C;
  opacity: 0.3;
}
.licence-wrapper p {
  font-size: 14px;
  font-weight: 400;
  line-height: 19px;
  color: #26262C;
  margin-bottom: 0;
}
.info.tc-icon.info-icon {
  width: 20px;
  height: 20px;
  margin-left: 50px;
}
</style>
