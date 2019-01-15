<template>
  <div class="main layui-clear">
    <h2 class="page-title">注册</h2>
    <div class="layui-form layui-form-pane">
      <form method="post">
        <div class="layui-form-item">
          <label for="L_username" class="layui-form-label">昵称</label>
          <div class="layui-input-inline">
            <input
              type="text"
              id="L_username"
              name="username"
              required
              lay-verify="required"
              autocomplete="off"
              class="layui-input"
            >
          </div>
        </div>
        <div class="layui-form-item">
          <label for="L_pass" class="layui-form-label">性别</label>
          <select>
            <option>男</option>
            <option>女</option>
          </select>
        </div>
        <div class="layui-form-item">
          <label for="L_email" class="layui-form-label">邮箱</label>
          <div class="layui-input-inline">
            <input
              type="email"
              id="L_email"
              name="email"
              required
              lay-verify="required"
              autocomplete="off"
              class="layui-input"
            >
          </div>
        </div>
        <div class="layui-form-item">
          <label for="L_pass" class="layui-form-label">密码</label>
          <div class="layui-input-inline">
            <input
              type="password"
              id="L_pass"
              name="password"
              required
              lay-verify="required"
              autocomplete="off"
              class="layui-input"
            >
          </div>
        </div>
        <div class="layui-form-item">
          <button class="layui-btn" lay-filter="*" lay-submit>注册</button>
          <span style="padding-left:20px;"></span>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
