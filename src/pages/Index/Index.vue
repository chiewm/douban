<template>
  <div>
    <header class="m-header is-fixed is-bg top-search">
      <div class="search-wrap">
        <img src="../../assets/images/ic_search_gray.png" alt="">
        <span class="placeholder">影视 图书 唱片 小组 舞台剧等</span>
        <!-- <img src="../../assets/images/ic_scan_gray.png" alt=""> -->
      </div>
      <div class="m-header-button is-right" style="text-align: center;width: 50px;">
        <a href="javascript:;"><img class="m-icon-img" src="../../assets/images/ic_chat_white.png" /></a>
      </div>
    </header>
    <div class="page-content">
      <m-cell title="提醒" icon>
        <img src="../../assets/images/ic_mine_notification.png" slot="icon">
        <a href="javascript:;" slot="cell-right"><img src="../../assets/images/ic_arrow_gray_small.png" alt=""></a>
      </m-cell>
      <m-cell title="设置">
        <a href="javascript:;" slot="cell-right"><img src="../../assets/images/ic_arrow_gray_small.png" alt=""></a>
      </m-cell>
    </div>
  </div>
</template>

<script>
import mTabbar from '../../components/tabbar'
import mTabbarItem from '../../components/tabbar-item'
import mHeader from '../../components/header'
import mCell from '../../components/cell'

export default {
  name: 'index',
  components: {
    mTabbar,
    mTabbarItem,
    mHeader,
    mCell
  },
  data() {
    return {
      select: 'tab1'
    }
  }
}
</script>
