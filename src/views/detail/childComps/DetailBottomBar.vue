<template>
  <div class="bottom-bar">
    <div class="bar-item bar-left">
      <div>
        <i class="icon service"></i>
        <span class="text">客服</span>
      </div>
      <div>
        <i class="icon shop"></i>
        <span class="text">店铺</span>
      </div>
      <div>
        <i class="icon select"></i>
        <span class="text">收藏</span>
      </div>
    </div>

    <div class="bar-item bar-right">
      <div class="cart" @click="addCart">加入购物车</div>
      <div class="buy">购买</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DetailBottomBar",
  data() {
    return {};
  },
  components: {},
  methods: {
    addCart() {
      this.$emit('addCart')
    }
  },
};
</script>

<style lang="less" scoped>
.bottom-bar {
  display: flex;
  text-align: center;
  height: 49px;
  background-color: #fff;
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  .bar-item {
    display: flex;
    flex: 1;
    div {
      flex: 1;
    }
    .text {
      font-size: 13px;
    }
    .icon {
      display: block;
      width: 22px;
      height: 22px;
      margin: 6px auto 3px;
      background: url("../../../assets/images/detail/detail_bottom.png")
        no-repeat;
      background-size: 100%;
    }
    .service {
      background-position: 0 -54px;
    }
    .shop {
      background-position: 0 -98px;
    }
  }

  .bar-right {
    font-size: 15px;
    color: #fff;
    line-height: 58px;
    .cart {
      background-color: #ffe817;
      color: #333;
    }
    .buy {
      background-color: #f69;
    }
  }
}
</style>
