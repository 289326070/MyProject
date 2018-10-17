<template>
  <div id="app">
    <v-header :seller="seller"></v-header>
    <div class='top' @click="myShow($event)">
      <router-link class="tab-item" :class="{active:ShopColor}" to="/" >商品</router-link>
      <router-link class="tab-item " :class="{active:DiscussColor}" to='Seller'>评论</router-link>
      <router-link class="tab-item" :class="{active:MerchantColor}" to='Retingss'>商家</router-link>
    </div>
    <router-view></router-view>
  </div>
</template>

<script>

import VHeader from './components/header/header.vue';
import Data from '../data.json';

export default {
  data () {
    return {
      seller: {},
      ShopColor: true,
      DiscussColor: false,
      MerchantColor: false
    };
  },
  created () {

  },
  mounted () {
    console.log('创建前');
     console.log(Data.seller);
     this.seller = Data.seller;
     console.log(this.seller);
  },
  methods: {
    /* 头部样式 */
     myShow ($event) {
       /* var e = $event.currentTarget.innerHTML; */
       var Text = $event.target.innerHTML;
        if (Text === '商品') {
         this.ShopColor = true;
           this.DiscussColor = false;
           this.MerchantColor =  false;
        }
        if (Text === '评论') {
           this.ShopColor = false;
           this.DiscussColor = true;
           this.MerchantColor =  false;
        }
        if (Text === '商家') {
          this.MerchantColor = true;
           this.ShopColor = false;
           this.DiscussColor = false;
        }
    }
  },
   components: {
    VHeader
   }
};
</script>

<style scoped>
  #app>.top{
    display:flex;
    width:100%;
    height:40px;
    line-height:40px;
    justify-content: space-around;
    border-bottom:1px solid rgba(7,17,27,0.1);
  }
   #app>.top>.tab-item{
     display:block;
     width:33.3%;
     border-size:border-box;
     text-align:center;
   }
   .active{
      color:red;
    }
</style>
