<template>
  <div>
     <swiper
      :indicator-dots="indicatorDots"
      :autoplay="autoplay"
      :interval="interval"
      :duration="duration"
      :indicator-color="indicatorColor"
      :indicator-active-color="indicatorActiveColor"
      style="height:220px"
     >
    <block v-for="img in imgUrls" :key="img">
      <swiper-item>
        <image :src="img" style="width:100%;"/>
      </swiper-item>
    </block>
    </swiper>
    
    <i-grid i-class="no-border">
    <i-grid-item @click="goType(grid)" v-for="grid in grids" :key="grid" i-class="no-border">
        <i-grid-icon>
            <image :src="grid.image" />
        </i-grid-icon>
        <i-grid-label>{{grid.title}}</i-grid-label>
    </i-grid-item>
    </i-grid>

  <i-panel :title="title_name"> 
    <view style="padding: 15px;">
      <i-card @click="goDetail(item)" v-for="item in top" :key="item" i-class="split" :title="item.name" :extra="item.introduce" :thumb="item.image">
        <view slot="content">{{item.remark}}</view>
        <view slot="footer">{{item.address}}</view>
      </i-card>
    </view>
   
  </i-panel>
 
  </div>
</template>

<script>

export default {
  data () {
    return {
      title_name:"本季推荐",
      grids:[
        {title:"圣罗兰",image:"/static/images/4.png"},
        {title:"阿玛尼",image:"/static/images/11.png"},
        {title:"MAC",image:"/static/images/9.png"},
        {title:"迪奥",image:"/static/images/12.png"}
        
      ],
      top:[
        {name:"999",introduce:"✔黄黑皮友好",address:"本宫不死，尔等终究是妃",image:"/static/images/999.jpg",remark:"Dior迪奥·烈焰蓝金唇膏"},        
        {name:"Chili",introduce:"✔黄黑皮友好",address:"国民挚爱，经典小辣椒，显白第一名！",image:"/static/images/c.jpg",remark:"MAC魅可·子弹头口红"},
        {name:"Marrakesh",introduce:"✔黄黑皮友好",address:"MAC2019新色，超火断货王！",image:"/static/images/M.jpg",remark:"MAC魅可·子弹头口红"},
        {name:"307",introduce:"❤",address:"复古宝石红",image:"/static/images/307.jpg",remark:"纪梵希·小羊皮唇膏"},
        {name:"405",introduce:"✔黄黑皮友好",address:"显白烂番茄",image:"/static/images/405.jpg",remark:"Amani·红管唇釉"}
      ],
      imgUrls: [
        "cloud://yunxin1-c2uai.7975-yunxin1-c2uai-1300857665/2.jpg",
        "cloud://yunxin1-c2uai.7975-yunxin1-c2uai-1300857665/1.jpg",
        "cloud://yunxin1-c2uai.7975-yunxin1-c2uai-1300857665/3.jpg"
      ],
      
      indicatorDots: true,
      autoplay: false,
      interval: 5000,
      duration: 1000,
      indicatorColor:"white",
      indicatorActiveColor:"#FFD700"
    }
  },

  methods: {
    
    goType(type){
      console.log(type)
      let url = '../list/main?type=' + type.title
      mpvue.navigateTo({ url })
   },
    goDetail(type){
      console.log(type)
      let url = '../detail/main?type=' + type.name
      mpvue.navigateTo({ url })
   }
  },

  
}
</script>

<style scoped>
div >>> .no-border {
  border-width: 0pt;
}
div >>> .split {
  margin-bottom: 10pt;
}

</style>
