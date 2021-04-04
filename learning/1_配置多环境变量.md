# 配置多环境变量

过在 package.json 里的 scripts 配置项中添加--mode xxx 来选择不同环境

只有以 VUE_APP 开头的变量会被 webpack.DefinePlugin 静态嵌入到客户端侧的包中，代码中可以通过 process.env.VUE_APP_BASE_API 访问

NODE_ENV 和 BASE_URL 是两个特殊变量，在代码中始终可用

配置
  在项目根目录中新建.env, .env.production, .env.analyz 等文件

* .env
  serve 默认的本地开发环境配置
```shell
NODE_ENV = "development"
BASE_URL = "./"
VUE_APP_PUBLIC_PATH = "./"
VUE_APP_API = "https://test.staven630.com/api"
```

* .env.production
  build 默认的环境配置（正式服务器）
```shell
NODE_ENV = "production"
BASE_URL = "https://prod.staven630.com/"
VUE_APP_PUBLIC_PATH = "https://prod.oss.com/staven-blog"
VUE_APP_API = "https://prod.staven630.com/api"

ACCESS_KEY_ID = "xxxxxxxxxxxxx"
ACCESS_KEY_SECRET = "xxxxxxxxxxxxx"
REGION = "oss-cn-hangzhou"
BUCKET = "staven-prod"
PREFIX = "staven-blog"
```

* .env.crm
  自定义 build 环境配置（预发服务器）
```shell
NODE_ENV = "production"
BASE_URL = "https://crm.staven630.com/"
VUE_APP_PUBLIC_PATH = "https://crm.oss.com/staven-blog"
VUE_APP_API = "https://crm.staven630.com/api"

ACCESS_KEY_ID = "xxxxxxxxxxxxx"
ACCESS_KEY_SECRET = "xxxxxxxxxxxxx"
REGION = "oss-cn-hangzhou"
BUCKET = "staven-crm"
PREFIX = "staven-blog"

IS_ANALYZE = true;
```
> 修改 package.json
```json
"scripts": {
  "build": "vue-cli-service build",
  "crm": "vue-cli-service build --mode crm"
}
```

使用环境变量

```vue
<template>
  <div class="home">
    <!-- template中使用环境变量 -->
     API: {{ api }}
  </div>
</template>

<script>
export default {
  name: "home",
  data() {
    return {
      api: process.env.VUE_APP_API
    };
  },
  mounted() {
    // js代码中使用环境变量
    console.log("BASE_URL: ", process.env.BASE_URL);
    console.log("VUE_APP_API: ", process.env.VUE_APP_API);
  }
};
</script>
```