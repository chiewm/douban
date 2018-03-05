<template>
  <div>
    <m-header title="豆瓣app" fixed :bg="true">
      <a href="javascript:;" slot="right"><img class="m-icon-img margin-right-10" src="../../assets/images/ic_actionbar_search_icon.png"/></a>
      <a href="javascript:;" slot="right"><img class="m-icon-img" src="../../assets/images/ic_chat_green.png"/></a>
    </m-header>

     <div class="page-content">
      <!-- <m-swipe swipeid="swipe01" :autoplay="1000" paginationDirection="right">
        <div class="swiper-slide " slot="swiper-con"><img src="../../assets/images/banner/01.jpg" alt=""></div>
        <div class="swiper-slide " slot="swiper-con"><img src="../../assets/images/banner/02.jpg" alt=""></div>
        <div class="swiper-slide " slot="swiper-con"><img src="../../assets/images/banner/03.jpg" alt=""></div>
      </m-swipe> -->
      <m-cell title="提醒" icon>
        <img src="../../assets/images/ic_mine_notification.png" slot="icon">
        <a href="javascript:;" slot="cell-right"><img src="../../assets/images/ic_arrow_gray_small.png" alt=""></a>
      </m-cell>
      <m-cell title="设置">
        <a href="javascript:;" slot="cell-right"><img src="../../assets/images/ic_arrow_gray_small.png" alt=""></a>
      </m-cell>

      <!--热门-->
      <div class="hot-wrap">
        <m-cell title="热门" label="hot">
          <!--<a href="javascript:;" slot="cell-right">更多<img src="../../assets/images/ic_arrow_gray_small.png" alt=""></a>-->
        </m-cell>
        <m-cell-media :author="item.target.author.name" :column="item.source_cn" :img="item.target.cover_url" v-for="item in hotData"
          :key="item.id">

          <span slot="title">{{item.title}}</span>
          <span slot="describe">{{item.target.desc}}</span>
        </m-cell-media>
      </div>
      </div>


  </div>
</template>

<script>
import mTabbar from '../../components/tabbar'
import mTabbarItem from '../../components/tabbar-item'
import mHeader from '../../components/header'

export default {
  name: 'index',
  components: {
    mTabbar,
    mTabbarItem,
    mHeader
  },
  data() {
    return {
      select: 'tab1'
    }
  }
}
</script>
