<template>
  <li :class="mainClass">
    <div class="balance-wrapper">
      <div class="main-balance">
        <div class="icon-wrapper">
          <i class="tc-icon balance-icon"></i>
        </div>
        <p>
          <span>MAIN BALANCE</span>
          722 897.00
        </p>
      </div>
      <div class="available-balance d-flex align-items-center">
        <div class="icon-wrapper">
          <i class="tc-icon balance2-icon"></i>
        </div>
        <p>
          <span>MAIN BALANCE</span>
          722 897.00
        </p>
      </div>
    </div>
  </li>
</template>

<script>
export default {
  name: "TcBalanceInfo",
  props:{
    mainClass:{
      type: String,
      default: ''
    }
  }
}
</script>

<style scoped>
.main-balance {
  display: flex;
  align-items: center;
  margin-right: 25px;
}
.main-balance p,
.available-balance p{
  font-size: 14px;
  font-weight: 400;
  line-height: 19px;
  color: #26262C;
  margin-bottom: 0;
}
.main-balance span,
.available-balance span {
  display: block;
  text-transform: uppercase;
  font-size: 10px;
  font-weight: 400;
  line-height: 14px;
  color: #26262C;
  opacity: 0.3;
}
.balance-wrapper {
  display: flex;
  padding: 20px 30px;
  border-right: 1px solid #e9ecef;
}
.icon-wrapper {
  width: 35px;
  height: 35px;
  background: #fff;
  border-radius: 50%;
  margin-right: 7px;
  position: relative;
}
.icon-wrapper i {
  width: 25px;
  height: 25px;
  position: absolute;
  top: 5px;
  left: 5px;
}
</style>
