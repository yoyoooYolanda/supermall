<template>
  <div class="goods">
    <goods-list-item v-for = "(item ,index) in goods" 
                      :key="index" 
                      :goods-item="item"/>
  </div>
</template>

<script>
import GoodsListItem from './GoodsListItem.vue'

export default {
  name: "GoodsList",
  props: {
    goods: {
      type: Array,
      default() {
        return []
      }
    }
  },
  components: {
    GoodsListItem
  }
}
</script>

<style>
  .goods {
    display: flex;
    flex-wrap: wrap;
    padding: 2px;
    justify-content: space-around;
  }
</style>