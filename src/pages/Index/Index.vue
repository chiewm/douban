<template>
  <div>
    <m-header title="豆 瓣" :bg="true" fixed>
    </m-header>
    <div class="page-content">
      <m-cell title="提醒" icon>
        <img src="../../assets/images/ic_mine_notification.png" slot="icon">
        <a href="javascript:;" slot="cell-right">
          <img src="../../assets/images/ic_arrow_gray_small.png" alt="">
        </a>
      </m-cell>
      <m-cell title="设置">
        <a href="javascript:;" slot="cell-right">
          <img src="../../assets/images/ic_arrow_gray_small.png" alt="">
        </a>
      </m-cell>
      <m-media-cell author="作者：大象公会" column="来自栏目：广播精选" img="https://img3.doubanio.com/view/note/large/public/p41141236.jpg">
        <span slot="title">个人意见：为什么中国没有鲍勃·迪伦这样的民谣歌手</span>
        <span slot="describe">我们这一代人的成长年代，真正的诗歌课从来都是缺席的。</span>
      </m-media-cell>
    </div>
  </div>
</template>

<script>
import mTabbar from '../../components/tabbar'
import mTabbarItem from '../../components/tabbar-item'
import mHeader from '../../components/header'
import mCell from '../../components/cell'
import mMediaCell from '../../components/media-cell'

export default {
  name: 'index',
  components: {
    mTabbar,
    mTabbarItem,
    mHeader,
    mCell,
    mMediaCell
  },
  data() {
    return {
      select: 'tab1'
    }
  }
}

</script>

<style lang="less">
header.m-header {
  padding: 0 0 0 10px;
}

.is-fixed ~ .page-content {
  padding-top: 44px;
  padding-bottom: 50px;
}

.top-search {
  .search-wrap {
    width: 100%;
    height: 30px;
    background: #fff;
    border-radius: 4px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    color: #c0c0c0;
    padding: 0 12px;
    .placeholder {
      flex: 1;
      text-align: left;
      padding-left: 12px;
    }
    img {
      width: 20px;
      height: 20px;
    }
  }
}

.hot-wrap,
.recommend-wrap {
  padding-top: 12px;
}
</style>
