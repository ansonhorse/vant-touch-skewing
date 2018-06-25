<!--
 触摸偏移测试

 @name Test
 @author Anxon <ansonhorse@gmail.com>
-->
<template>
  <div class="item-detail">
    <!-- 商品header -->
    <!--<van-nav-bar
      title="标题"
      left-text="返回"
      right-text="按钮"
      left-arrow
    />-->

    <!-- 描述 -->
    <div class="item-desc">
      <h1 v-for="i in 80">{{ 'hello' + i}}</h1>
    </div>

    <van-sku
      v-model="showBase"
      :sku="sku"
      :goods="goods"
      :goods-id="goodsId"
      :hide-stock="sku.hide_stock"
      close-on-click-overlay
      @buy-clicked="onBuyClicked"
      @add-cart="onAddCartClicked"
    />

    <!-- 商品footer -->
    <van-goods-action>
      <van-goods-action-mini-btn icon="chat" text="客服" @click="onClickChat"/>
      <van-goods-action-mini-btn icon="cart" text="购物车" @click="onClickCart"/>
      <van-goods-action-big-btn text="加入购物车" @click="add"/>
    </van-goods-action>
  </div>
</template>

<script>
  export default {
    components: {},
    data() {
      return {
        nn: 0,
        showBase: false,

        sku: {
          // 所有sku规格类目与其值的从属关系，比如商品有颜色和尺码两大类规格，颜色下面又有红色和蓝色两个规格值。
          // 可以理解为一个商品可以有多个规格类目，一个规格类目下可以有多个规格值。
          tree: [
            {
              k: '颜色', // skuKeyName：规格类目名称
              v: [
                {
                  id: '30349', // skuValueId：规格值 id
                  name: '红色', // skuValueName：规格值名称
                  imgUrl: 'https://img.yzcdn.cn/upload_files/2017/02/21/FjKTOxjVgnUuPmHJRdunvYky9OHP.jpg!100x100.jpg' // 规格类目图片，只有第一个规格类目可以定义图片
                },
                {
                  id: '1215',
                  name: '蓝色',
                  imgUrl: 'https://img.yzcdn.cn/upload_files/2017/03/16/Fs_OMbSFPa183sBwvG_94llUYiLa.jpeg?imageView2/2/w/100/h/100/q/75/format/jpg'
                }
              ],
              k_s: 's1' // skuKeyStr：sku 组合列表（下方 list）中当前类目对应的 key 值，value 值会是从属于当前类目的一个规格值 id
            }
          ],
          // 所有 sku 的组合列表，比如红色、M 码为一个 sku 组合，红色、S 码为另一个组合
          list: [
            {
              id: 2259, // skuId，下单时后端需要
              price: 100, // 价格（单位分）
              s1: '1215', // 规格类目 k_s 为 s1 的对应规格值 id
              s2: '1193', // 规格类目 k_s 为 s2 的对应规格值 id
              s3: '0', // 最多包含3个规格值，为0表示不存在该规格
              stock_num: 110 // 当前 sku 组合对应的库存
            }
          ],
          price: '1.00', // 默认价格（单位元）
          stock_num: 227, // 商品总库存
          collection_id: 2261, // 无规格商品 skuId 取 collection_id，否则取所选 sku 组合对应的 id
          none_sku: false, // 是否无规格商品
          messages: [
            {
              // 商品留言
              datetime: '0', // 留言类型为 time 时，是否含日期。'1' 表示包含
              multiple: '0', // 留言类型为 text 时，是否多行文本。'1' 表示多行
              name: '留言', // 留言名称
              type: 'text', // 留言类型，可选: id_no（身份证）, text, tel, date, time, email
              required: '1' // 是否必填 '1' 表示必填
            }
          ],
          hide_stock: false // 是否隐藏剩余库存
        },

        goods: {
          // 商品标题
          title: '测试商品',
          // 默认商品 sku 缩略图
          picture: 'https://img.yzcdn.cn/upload_files/2017/02/21/FjKTOxjVgnUuPmHJRdunvYky9OHP.jpg!100x100.jpg'
        },

        goodsId: '12345678',

        closeOnClickOverlay: this.onCloseSku,
      }
    },
    methods: {
      onClickChat() {
        this.$toast('客服 ' + this.nn++)
      },
      onClickCart() {
        this.$toast('购物车 ' + this.nn++)
      },
      add() {
        this.$toast('打开sku ' + this.nn++)
        // this.showBase = true
      },
      onCloseSku() {
        this.showBase = false
      },
      onBuyClicked() {

      },
      onAddCartClicked() {

      }
    }
  }
</script>

<style>

</style>
