<template>
<!-- one-top-px    添加1像素上边框 -->
  <nav class="tabs one-top-px">
      <!--router-link相当于a标签   :key  加入key值,不再读取缓存中的数据   :to相当于href -->
      <router-link class="tab" v-for="(tabItem, index) in tabsData" 
        :key="index" :to="tabItem.path">
          {{tabItem.title}}
      </router-link>
  </nav>
</template>

<script>
export default {
    //统一为该组件命名
    name: 'tabs',
    //避免变量暴露,所以用函数包起来
    data(){
        return {
            tabsData: [
                {title: '首页', path: '/home'},
                {title: '发现', path: '/discover'},
                {title: '订单', path: '/order'},
                {title: '我的', path: '/mine'},
            ]
        }
    }
}
</script>

<style scoped>
.tabs{
    position: absolute;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 49px;
    display: flex;
    background: #fff;
}
.tabs .tab{
    flex: 1;
    text-align: center;
    line-height: 49px;
    color: #8e8e93;
}
.tabs .tab.router-link-active{
    color: #0089dc;
}

</style>
