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

      <m-media-cell :author="item.target.author.name" :column="item.source_cn" :img="item.target.cover_url" v-for="(item) in hotData"


        :key="item.id">

        <span slot="title">{{item.title}}</span>
        <span slot="describe">{{item.target.desc}}</span>
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
      recommendData: [],
      hotData: []
    }
  },
  created() {
    this.fetchData()
  },
  methods: {
    fetchData() {
      this.axios.get('/api').then((response) => {
        let data = response.data.data.recommend_feeds
        let recommend = []
        let hot = []
        for (var i in data) {
          if (data[i].card && data[i].card.name == '为你推荐') {
            recommend.push(data[i])
          } else {
            hot.push(data[i])
          }
        }

        this.recommendData = recommend
        this.hotData = hot

      })
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
