<template>
  <div class="main layui-clear">
    <h2 class="page-title">登入</h2>
    <div class="layui-form layui-form-pane">
      <form method="post">
        <div class="layui-form-item">
          <label for="L_email" class="layui-form-label">邮箱</label>
          <div class="layui-input-inline">
            <input
              type="text"
              id="L_email"
              name="username"
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
          <button class="layui-btn" lay-filter="*" lay-submit>立即登录</button>
          <span style="padding-left:20px;"></span>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  created() {
    this.init();
  },
  data() {
    return {};
  },
  methods: {
    init() {
      let _this = this;
      layui.use(["form", "layedit"], function() {
        var form = layui.form(),
          layer = layui.layer;
        //监听提交
        form.on("submit(*)", function(data) {
          _this.$store
            .dispatch("login", data.field)
            .then(() => {
              _this.$store.dispatch("getLoginUser").then(() => {
                _this.$router.push({
                  path: "/"
                });
              });
            })
            .catch(error => {
              layer.msg("登录失败:" + error);
            });
          return false;
        });
      });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
