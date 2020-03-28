<template>
  <div class="header">
    <div class="main w">
      <!-- logo -->
      <div class="logo">
        <nuxt-link to="/">
          <img src="http://157.122.54.189:9093/images/logo.jpg" alt />
        </nuxt-link>
      </div>
      <!-- nav -->
      <div class="nav">
        <div class="navs">
          <!-- <nuxt-link to="/">首页</nuxt-link>
          <nuxt-link to="/post">旅游攻略</nuxt-link>
          <nuxt-link to="/hotel">酒店</nuxt-link>
          <nuxt-link to="/air">国内机票</nuxt-link> -->
          <nuxt-link :to="item.url" v-for="(item, index) in nav" :key="index">{{
            item.name
          }}</nuxt-link>
        </div>
      </div>
      <!-- login 注册 / 登录-->
      <div class="login">
        <el-dropdown v-if="aa">
          <div class="user">
            <img
              src="http://157.122.54.189:9095/assets/images/avatar.jpg"
              alt=""
            />
            <div class="username">
              管理员
              <div class="el-icon-caret-bottom"></div>
            </div>
          </div>
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item>个人中心</el-dropdown-item>
            <el-dropdown-item>退出</el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
        <div v-else class="member">注册 / 登录</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nav: [
        {
          name: "首页",
          url: "/"
        },
        {
          name: "旅游攻略",
          url: "/post"
        },
        {
          name: "酒店",
          url: "/hotel"
        },
        {
          name: "国内机票",
          url: "/air"
        }
      ],
      aa: true
    };
  }
};
</script>
<style lang="less" scoped>
.header {
  width: 100%;
  height: 60px;
  border-bottom: 1px solid #ddd;
  .main {
    height: 100%;
    display: flex;
    .logo {
      width: 156px;
      padding-top: 10px;
    }
    .nav {
      flex: 1;
      margin: 0 20px;
      .navs {
        width: 60%;
        height: 60px;
        display: flex;
        a {
          width: 100%/4;
          font-size: 16px;
          display: flex;
          justify-content: center;
          align-items: center;
          &:hover {
            color: #409eff;
            border-bottom: 5px #409eff solid;
          }
        }
        .nuxt-link-exact-active {
          background: #409eff;
          color: #fff;
          &:hover {
            color: #fff;
          }
        }
      }
    }
    .login {
      font-size: 16px;
      width: 120px;
      height: 60px;
      display: flex;
      justify-content: center;
      align-items: center;
      .member {
      }
      .user {
        display: flex;
        align-items: center;
        img {
          width: 36px;
          height: 36px;
        }
      }
    }
  }
}
</style>
