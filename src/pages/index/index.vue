<template>
  <div>
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
      <i-card v-for="item in top" :key="item" i-class="split" :title="item.name" extra="额外内容" :thumb="item.image">
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
      title_name:"推荐啦啦啦~",
      grids:[
        {title:"吃喝",image:"/static/images/2.png"},
        {title:"玩乐",image:"/static/images/4.png"},
        {title:"穿搭",image:"/static/images/8.png"}
      ],
      top:[
        {name:"店名1",address:"地址1",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍1"},        
        {name:"店名2",address:"地址2",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍2"},
        {name:"店名3",address:"地址3",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍3"},
        {name:"店名4",address:"地址4",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍4"},
        {name:"店名5",address:"地址5",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍5"},
        {name:"店名6",address:"地址6",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍6"}
      ]
    }
  },

  methods: {
    goType(type){
      console.log(type)
      
    }
  },

  created () {
  }
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
