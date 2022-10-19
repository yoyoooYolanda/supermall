<template>
  <div class="tab-control">
    <div v-for="(item, index) in titles" 
      :key="index" class="tab-control-item"
      @click="currentIndex = index"
      :class="currentIndex == index? 'active':''">
      <span>{{item}}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "TabControl",
  props: {
    titles: {
      type: Array,
      default() {
        return []
      }
    }
  },
  data() {
    return {
      currentIndex: 0
    }
  }
}
</script>

<style>
  .tab-control {
    display: flex;
    height: 40px;
    line-height: 40px;
    font-size: 15px;
    background-color: #fff;
  }
  .tab-control-item {
    flex: 1;
    text-align: center;
    
  }
  .tab-control-item span {
    padding: 0 8px 5px;
  }
  .active {
    color: var(--color-tint);
  }
  .active span {
    border-bottom: 3px solid var(--color-tint);
  }
</style>