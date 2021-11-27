<template>
  <el-row class="home" :gutter="20">
    <el-col :span="8" style="margin-top: 20px;">
      <el-card shadow="hover">
        <div class="user">
          <img :src="userImg" alt="">
          <div class="userinfo">
            <p class="name">Admin</p>
            <p class="access">超级管理员</p>
          </div>
        </div>
        <div class="login-info">
          <p>上次登录时间：<span>2021-11-27</span></p>
          <p>上次登录地点：<span>广州</span></p>
        </div>
      </el-card>
      <el-card style="margin-top: 20px;height: 510px;"  shadow="hover">
        <el-table :data="tableData">
          <el-table-column show-overflow-tooltip v-for="(val,key) in tableLabel" :key="key" :prop="key" :label="val"></el-table-column>
        </el-table>
      </el-card>
    </el-col>
    <el-col :span="16" style="margin-top: 20px;">
      <div class="num">
        <el-card shadow="hover" v-for="item in countData" :key="item.name" :body-style="{display: 'flex',padding: 0}">
          <i class="icon" :class="`el-icon-${item.icon}`" :style="{background: item.color}"></i>
          <div class="detail">
            <p class="number">￥{{item.value}}</p>
            <p class="text">￥{{item.name}}</p>
          </div>
        </el-card>
      </div>
      <el-card shadow="hover" style="height: 280px;"></el-card>
      <div class="graph">
        <el-card shadow="hover" style="height: 280px;"></el-card>
        <el-card shadow="hover" style="height: 280px;"></el-card>
      </div>
    </el-col>
  </el-row>
</template>

<script>
  export default {
    data() {
      return {
        userImg: require('../../assets/images/user.png'),
        tableData:[
          {
            name:"oppo",
            todayBuy: 100,
            monthBuy: 100,
            totalBuy: 594641,
          },
          {
            name:"vivo",
            todayBuy: 200,
            monthBuy: 200,
            totalBuy: 238482,
          },
          {
            name:"apple",
            todayBuy: 300,
            monthBuy: 300,
            totalBuy: 4598465,
          },
          {
            name:"xiaomi",
            todayBuy: 400,
            monthBuy: 400,
            totalBuy: 226666,
          },
          {
            name:"huawei",
            todayBuy: 500,
            monthBuy: 500,
            totalBuy: 849989,
          },
        ],
        tableLabel:{
          name:'课程',
          todayBuy:'今日购买',
          monthBuy:'当月购买',
          totalBuy:'总购买',
        },
        countData:[
          {
            name:'本月支付订单',
            value:'1234',
            icon:'success',
            color:'#2ec7c9',
          },
          {
            name:'本月收藏订单',
            value:'210',
            icon:'star-on',
            color:'#ffb980',
          },
          {
            name:'本月未支付订单',
            value:'1234',
            icon:'s-goods',
            color:'#5ab1ef',
          },
          {
            name:'本月支付订单2',
            value:'1234',
            icon:'success',
            color:'#2ec7c9',
          },
          {
            name:'本月收藏订单2',
            value:'210',
            icon:'star-on',
            color:'#ffb980',
          },
          {
            name:'本月未支付订单2',
            value:'1234',
            icon:'s-goods',
            color:'#5ab1ef',
          },
        ]
      }
    }
  }
</script>

<style scoped>
p{
  margin: 0;
  padding: 0;
}
.num{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
.num .el-card{
  width: 30%;
  height: 70px;
  margin-bottom: 10px;
}
.num .icon{
  width: 70px;
  height: 70px;
  line-height: 70px;
  text-align: center;
}
.detail .number{
  font-size: 18px;
}
.detail .text{
  font-size: 12px;
  color: grey;
}
.graph{
  margin-top: 20px;
  display: flex;
  justify-content: space-between;
}
.graph .el-card{
  width: 48%;
}
</style>