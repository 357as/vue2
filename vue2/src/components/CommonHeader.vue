<template>
  <div class="header-content">
    <div class="l-content">
      <el-button icon="el-icon-menu" @click="handleMenu" size="mini"></el-button>
      <!-- 面包屑 -->
     <span class="text">首页</span>
    </div>
    <div class="r-content">
      <el-dropdown>
        <span class="el-dropdown-link">
          <img class="user" src="../assets/user.jpg" alt />
          <i class="el-icon-arrow-down el-icon--right"></i>
        </span>
        <el-dropdown-menu slot="dropdown">
          <el-dropdown-item>个人中心</el-dropdown-item>
          <el-dropdown-item @click="logout">退出登录</el-dropdown-item>
        </el-dropdown-menu>
      </el-dropdown>
    </div>
  </div>
</template>
<script>
import {mapState} from 'vuex'
import cookoe from 'js-cookie'
import jsCookie from 'js-cookie';
export default {
  data() {
    return {};
  },
  methods:{
    handleMenu(){
      this.$store.commit('collapseMenu')
    },
    logout(){
      // jsCookie.remove('token')
      this.$route.push({nume:'login'})
      console.log(11111);
    },
   
  },
  // computed:{
  //   ...mapState({
  //     tags:state => state.tab.tabsList
  //   })
  // },
};
</script>
<style lang="less" scoped>
.header-content {
  background-color: #333;
  height: 60px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;
  .text {
    color: #fff;
    font-size: 14px;
    margin-left: 10px;
  }
  .r-content {
    .user {
      width: 40px;
      height: 40px;
      border-radius: 50%;
    }
  }
}
</style>