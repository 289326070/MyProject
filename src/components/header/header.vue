<template>
    <div class="header">
        <div class="content-wrapper">
            <div class="avatar">
                <img class='myImg' :src="seller.avatar" alt="">
                <div class='avatar-item'>
                    <h4 v-text='seller.name'></h4>
                    <h6 >{{seller.description}}/{{seller.deliveryTime}}分钟送达</h6>
                    <div class='avatar-item-list'>
                        <span v-text='seller.supports[0].description'></span>
                        <span>5个</span>
                    </div>
                </div>
            </div>
        </div>  
    </div>
</template>

<script>
    export default {
        props: ["seller"],
        created () {
            console.log(this.seller);
  },
}
</script>

<style>
    .header{
        background:#eee
    }
    .myImg{
        width:80px;
        height:80px;
        margin-left:20px;
    }
    .avatar{
        display:flex;
        justify-content:"center";
       padding:10px 20px;
    }
    .avatar-item{
        width:100%;
        text-align:center;
        padding:0 20px;
    }
    .avatar-item h4{
       font:600 18px/22px "";
        color:red
    }
     .avatar-item h6{
         text-align:left;
          font:400 14px/1em "";
          padding:10px 0;
     }
     .avatar-item-list{
        width:100%;
        text-align:left;
     }
     .avatar-item-list span:nth-child(1){  
        font: 14px/1em '';
     }
     .avatar-item-list span:nth-child(2){     
         display:inline-block;
         width:30px;
        padding:5px;
        border-radius:5px;
        background:#999;
        text-align:center;
       margin-left:30px;;
     }
</style>
