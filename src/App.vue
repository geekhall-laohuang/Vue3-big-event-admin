<script setup>
import { useRoute, useRouter } from 'vue-router'
import { useUserStore } from './stores'

const router = useRouter()
const route = useRoute()
const goList = () => {
  console.log(router, route) //
  router.push('/home')
}

const userStore = useUserStore()
</script>

<template>
  <router-view></router-view>

  <test-demo></test-demo>
  <div>app</div>
  <el-button @click="goList">2</el-button>
  <el-button type="primary">Primary</el-button>
  <el-button type="success">Success</el-button>

  <p>{{ userStore.token }}</p>
  <el-button @click="userStore.setToken('123')">登录</el-button>
  <el-button @click="userStore.removeToken()">退出</el-button>
</template>

<style scoped></style>
