<template>
  <div>
    <m-header title="豆瓣app" fixed :bg="true">
      <a href="javascript:;" slot="right"><img class="m-icon-img margin-right-10" src="../../assets/images/ic_actionbar_search_icon.png"/></a>
      <a href="javascript:;" slot="right"><img class="m-icon-img" src="../../assets/images/ic_chat_green.png"/></a>
    </m-header>
  </div>
</template>

<script>
import mTabbar from "../../components/tabbar";
import mTabbarItem from "../../components/tabbar-item";
import mHeader from "../../components/header"

export default {
  name: "index",
  components: {
    mTabbar,
    mTabbarItem,
    mHeader
  },
  data() {
    return {
      select: "tab1"
    };
  }
};
</script>
