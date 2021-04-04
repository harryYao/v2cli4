
# 配置 proxy 代理解决跨域问题

> vue文档地址 https://cli.vuejs.org/zh/config/#devserver-proxy   
> 完整选项文档地址（http-proxy-middleware） https://github.com/chimurai/http-proxy-middleware#proxycontext-config   
> 也可以查看 ./node_modules/http-proxy-middleware/readme.md

```
module.exports = {
  devServer: {
    proxy: {
      "/api": {
        target: "https://www.easy-mock.com/mock/5bc75b55dc36971c160cad1b/sheets", // 目标代理接口地址
        secure: false,
        changeOrigin: true, // 开启代理，在本地创建一个虚拟服务端
        // ws: true, // 是否启用websockets
        pathRewrite: {
          "^/api": "/"
        }
      }
    }
  }
};
```