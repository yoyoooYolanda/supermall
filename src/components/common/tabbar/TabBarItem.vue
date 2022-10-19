<template>
  <div class="tab-bar-item" @click="itemClick" :style="activeStyle">
    <!-- 将插槽包装到单独的div，避免替换时丢失插槽原有的属性 -->
    <div v-if="!isActive">
      <slot name="item-icon"></slot>
    </div>
    <div v-else>
      <slot name="item-icon-active"></slot>
    </div>
    <div >
      <slot name="item-text" ></slot>
    </div>
    
  </div>
</template>

<script>
export default {
  name: 'TabBarItem',
  data() {
    return {
      // isActive: true
    }
  },
  props: {
    path: String,
    activeColor: {
      type: String,
      default: 'pink'
    }
  },
  computed: {
    isActive() {
      //this.$route.path返回当前活跃的路由路径
      //str1.indexof(str2)返回str2在str1中首次出现的位置，若不存在则返回-1
      return this.$route.path.indexOf(this.path) != -1
    },
    activeStyle() {
      return this.isActive? {color: this.activeColor} : {}
    }
  },
  methods: {
    itemClick() {
      this.$router.replace(this.path)
    }
  }
}
</script>

<style>
.tab-bar-item {
  flex: 1;
  text-align: center;
  height: 46px;
  font-size: 14px;
  padding-top: 3px;
}
.tab-bar-item img {
  height: 24px;
}

</style>