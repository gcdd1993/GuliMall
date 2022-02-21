# 谷粒商城代码

> 看了前几集，感觉还是面面俱到，似乎也有一些微服务细节，值得一看

[视频地址](https://www.bilibili.com/video/BV1np4y1C7Yf)

# FAQ

## 前端项目如何运行？

```bash
$ node -v
v12.22.10
# 使用12版本的NodeJS，过高版本node-sass安装会失败
$ npm config set registry https://registry.npm.taobao.org
$ npm install
$ npm run dev
# ... 
```

## node-sass binary binary 404

修改`node-sass`版本为`4.12.0`

详情查看：https://stackoverflow.com/questions/63263601/cannot-download-node-sass-http-error-404-not-found-node-gyp-error

