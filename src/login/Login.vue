<script setup lang="ts">
import { reactive } from 'vue'
import bgImage from './imgs/bg.png'
import flagEnImage from './imgs/flag-en.svg'
import footerImage from './imgs/footer.png'
import Down from './imgs/svg/Down.vue'
import FlagEn from './imgs/svg/FlagEn.vue'

const formData = reactive({
  username: '',
  password: '',
})
</script>

<template>
  <div class="login">
    <div class="main-content">
      <div class="left hidden sm:block">
        <el-image :src="bgImage"></el-image>
      </div>
      <div class="right border-1 border-gray-200">
        <header class="w-full flex justify-end py-10 px-16">
          <el-dropdown trigger="click">
            <span class="cursor-pointer flex items-center gap-1">
              <flag-en class="mr-2"></flag-en>
              <span class="text-xl text-black">英文/EN</span>
              <el-icon class="el-icon--right">
                <down></down>
              </el-icon>
            </span>
            <template #dropdown>
              <el-dropdown-menu>
                <el-dropdown-item>英文/EN</el-dropdown-item>
                <el-dropdown-item>中文/ZH</el-dropdown-item>
              </el-dropdown-menu>
            </template>
          </el-dropdown>
        </header>
        <el-form
          style="width: 352px"
          :model="formData"
          ref="vForm"
          label-position="top"
          label-width="80px"
          class="my-form"
          @submit.prevent
        >
          <el-form-item label="账号" prop="username">
            <el-input
              v-model="formData.username"
              type="text"
              size="large"
              clearable
            ></el-input>
          </el-form-item>
          <el-form-item label="密码" prop="password">
            <el-input
              v-model="formData.password"
              type="password"
              clearable
              show-password
            ></el-input>
          </el-form-item>

          <el-button color="#808080" style="color: white" class="w-full mt-4">
            <span
              class="text-white text-2xl font-bold tracking-widest"
              style="letter-spacing: 20px; text-indent: 20px"
              >登录</span
            ></el-button
          >
        </el-form>
        <footer class="mb-18"><img :src="footerImage" /></footer>
      </div>
    </div>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.my-form .el-form-item__label {
  letter-spacing: 1rem;
  font-weight: 600;
  font-size: 23px;
  line-height: 2rem !important;
}
</style>
<style scoped lang="scss">
:deep(.el-button) {
  height: 49px;
  border-radius: 12px;
}

.login {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

.main-content {
  height: 975px;
  display: flex;
}

.left {
  width: 1223px;
  height: 100%;
  flex-shrink: 0;
  overflow: hidden;
}

.right {
  flex-shrink: 0;
  width: 697px;
  height: 100%;
  display: inline-flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
}
</style>
