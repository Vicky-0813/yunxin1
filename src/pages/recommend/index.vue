<template>
  <div  style="background-image:url(/static/images/4.jpeg);">
    <i-panel :title="title_name">
    <view style="padding: 15px; background-image:url(/static/images/4.jpeg);">
    <i-row>
    <i-col span="12" i-class="col-class">
      <i-card  style="padding:15px" v-for="item in discuss" :key="item" i-class="split" :title="item.name" :thumb="item.image">
        <view slot="content">{{item.remark}}</view>
        <view slot="footer">{{item.address}}</view>
      </i-card>
    </i-col>
    <i-col span="12" i-class="col-class">
      <i-card style="padding:15px" v-for="item in share" :key="item" i-class="split" :title="item.name"  :thumb="item.image">
        <view slot="content">{{item.remark}}</view>
        <view slot="footer">{{item.address}}</view>
      </i-card>
    </i-col>
   </i-row>
   </view>
    </i-panel>
  </div>
</template>

<script>

export default {
  data () {
    return {
      title_name:"最新试色",
      discuss:[
        {name:"Chili",address:"真的很显白！日常带妆都很适合",image:"/static/images/试色1.jpg",remark:"MAC·柔感哑光唇膏"},        
        {name:" ",address:" ",image:"/static/images/试色2.jpg",remark:"分享给大家hhhh"},
        {name:"Blush",address:"非常正宗的豆沙色了，哑光质地，持久度也比较高",image:"/static/images/试色6.jpg",remark:"3ce 爱茉莉"},
        {name:"224",address:"有点水红色的感觉，比较容易掉，但是口红就是要用呀",image:"/static/images/试色7.jpg",remark:"香奈儿黑管唇膏"},
        {name:"547",address:" ",image:"/static/images/试色9.jpg",remark:"L.A girl"}
      ],
      share:[
        {name:"10",address:"买它！！什么神仙颜色！！",image:"/static/images/试色4.jpg",remark:"圣罗兰镜光唇釉"},        
        {name:"05",address:"是一支复古红，无敌显白",image:"/static/images/试色5.jpg",remark:"CINDY & NICK 丝绒雾面口红"},
        {name:"Arriba",address:"显白是显白，但干也是真的干_(:з」∠)_ ",image:"/static/images/试色8.jpg",remark:"colorpop细管口红"},
        {name:"Hang up",address:"这只口红让我感觉自己像融化了的巫婆",image:"/static/images/试色3.jpg",remark:"MAC·水漾润泽唇膏"}
      ]
    }
  },

  methods: {
   
  },

  created () {
  }
}
</script>

<style scoped>
</style>
