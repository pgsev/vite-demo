<script>
import { reactive } from 'vue';

export default {
  setup() {
    const loginForm = reactive({
      username: '',
      password: '',
    });

    const handleLogin = () => {
      console.log('登录请求:', loginForm);
    };

    return {
      loginForm,
      handleLogin,
    };
  },
};
</script>

<template>
  <el-form :model="loginForm" label-width="80px" class="login-form">
    <el-form-item label="用户名" class="el-form-item">
      <el-input v-model="loginForm.username" autocomplete="off" class="full-width-input"></el-input>
    </el-form-item>
    <el-form-item label="密码" class="el-form-item">
      <el-input type="password" v-model="loginForm.password" autocomplete="off" class="full-width-input"></el-input>
    </el-form-item>
    <el-form-item>
      <el-button type="primary" class="full-width-button" @click="handleLogin">登录</el-button>
    </el-form-item>
  </el-form>
</template>



<style>
.login-form .el-form-item {
  text-align: justify;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-right: 16px; /* 调整此值以适应星号和标签之间的间距 */}

.full-width-input,
.full-width-button {
  width: 100%; /* 尝试填充父容器宽度，但通常会被表单项的布局限制 */
  max-width: 300px; /* 设置一个最大宽度，使输入框和按钮有相同的最大宽度 */
}

/* 注意：如果表单项（el-form-item）有默认的padding或margin，你可能需要调整这些值 */
</style>