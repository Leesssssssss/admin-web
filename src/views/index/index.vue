<template>
  <el-container>
    <el-header class='header-container'>后台管理</el-header>
    <el-container>
      <el-aside width="200px">
        <el-menu
        :default-active="defaultActive"
        class="el-menu-vertical-demo"
        background-color="#545c64"
        text-color="#fff"
        active-text-color="#ffd04b"
        router>
          <el-menu-item index="addgoods">
            <i class="el-icon-menu"></i>
            <span slot="title">发布商品</span>
          </el-menu-item>
          <el-menu-item index="goods">
            <i class="el-icon-setting"></i>
            <span slot="title">商品管理</span>
          </el-menu-item>
          <el-menu-item index="orders">
            <i class="el-icon-setting"></i>
            <span slot="title">订单管理</span>
          </el-menu-item>
        </el-menu>
      </el-aside>
      <el-container>
        <el-main>
          <router-view></router-view>
        </el-main>
      </el-container>
    </el-container>
  </el-container>
</template>

<script>
export default {
  data() {
    return{
      defaultActive: 'addgoods'
    }
  },
  created() {
    console.log(this.$route.path.substring(1));
    this.setActive();
  },
  methods: {
    setActive() {
      this.defaultActive = this.$route.path.substring(1)
    }
  }
};
</script>

<style lang="scss" scoped>
.header-container {
  font-size: 34px;
  font-weight: 700;
  background-color: #545c64;
  color: #ffd04b;
  margin-bottom: 5px;
  text-align: center;
}
</style>
