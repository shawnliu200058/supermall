<template>
  <div class="tab-bar-item" @click="itemClick">
    <div v-if="!isActive"><slot name="item-icon"></slot></div>
    <div v-else><slot name="item-icon-active"></slot></div>
    <div :style="activeStyle"><slot name="item-text"></slot></div>
  </div>
</template>

<script>
export default {
  name: "TabBarItem",
  data() {
    return {
      
    };
  },
  props: {
    path: String,
    activeColor: {
      type: String,
      default: 'red'
    }
  },
  methods: {
    itemClick() {
      this.$router.replace(this.path).catch(err => err)
    }
  },
  computed: {
    isActive() {
      return this.$route.path.includes(this.path)
    },
    activeStyle() {
      return this.isActive ? {color: this.activeColor} : {}
    }
  },
  components: {},
};
</script>

<style scoped>
.tab-bar-item {
  flex: 1;
  text-align: center;
  height: 49px;
  margin-top: 3px;
  font-size: 14px;
}
.tab-bar-item img {
  width: 24px;
}
.active {
  color: red;
}
</style>
