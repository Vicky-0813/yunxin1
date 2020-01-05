<template>
  <div>
    <i-panel v-for="item in detail" :key="item" >
      <view style="padding: 20px 15px 222px; background-image:url(/static/images/背景5.jpeg);">
      <view class="Size1">{{item.name}}</view>
      <view style="padding: 15px 5px;color:#FFFFFF" class="Size2"><br/>{{item.remark1}}<br/>{{item.remark2}}</view>
      <view style="padding: 10px 5px;">{{item.introduce}}</view>
      <view style="color:#FFD700">{{item.grade}}</view>
      <view style="padding: 10px 5px;">介绍：{{item.detail}}</view>
      <view style="padding: 15px 5px;" class="Size3">试 色</view>
      <image :src="item.image" />
      </view>
    </i-panel>  
  </div>
</template>

<script>

export default {
  data () {
    return {
      detail:{ },
    }
  },
  onLoad (option){
    console.log(option.type)
    this.detail = require('@/data/' + option.type + '.json')
    console.log(this.detail)
  },

 
}
</script>

<style scoped>
.Size1{
  font-size: 30px;
  font-weight:500;
}
.Size2{
  font-size: 14px;
}
.Size3{
  font-weight:400;
}
</style>
