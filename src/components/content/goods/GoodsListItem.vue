<template>
  <div class="goods-item">
    <img :src="goodsItem.show.img" alt=""/>
    <div class="goods-info">
      <p>{{goodsItem.props[0]}}</p>
      <span class="price">{{goodsItem.price}}</span>
      <span class="collect">{{goodsItem.cfav}}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "GoodsListItem",
  props: {
    goodsItem: {
      type: Object,
      default() {
        return {}
      }
    }
  }
}
</script>

<style>
  .goods-item {
    width: 48%;
    position: relative;
  }
  .goods-item img {
    width: 100%;
    border-radius: 5px;
    margin-bottom: 40px;
  }
  .goods-info {
    width: 100%;
    font-size: 12px;
    text-align: center;
    position: absolute;
    bottom: 5px;
    left: 0;
  }
  .goods-info p {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }
  .goods-info .price {
    color: var(--color-tint);
    margin-right: 20px;
  }
  .goods-info .collect {
    position: relative;
  }
  .goods-info .collect::before {
    content: '';
    width: 14px;
    height: 14px;
    position: absolute;
    left: -15px;
    top: -1px;
    background: url('~assets/img/common/collect.svg') center;
    background-size: contain;
  }
</style>