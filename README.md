# 乐优商城

## 跨域问题解决

https://github.com/coder-lzh/leyou/blob/master/day06-webpack/day06.md#63cors%E8%A7%A3%E5%86%B3%E8%B7%A8%E5%9F%9F

## 异步查询工具axios
https://github.com/coder-lzh/leyou/blob/master/day06-webpack/day06.md#73%E5%BC%82%E6%AD%A5%E6%9F%A5%E8%AF%A2%E5%B7%A5%E5%85%B7axios

## qs工具的使用
https://github.com/coder-lzh/leyou/blob/master/day08-%E5%93%81%E7%89%8C%E7%AE%A1%E7%90%86/day08-%E5%93%81%E7%89%8C%E7%AE%A1%E7%90%86.md#132qs%E5%B7%A5%E5%85%B7

## 子组件调用父组件方法
https://github.com/coder-lzh/leyou/blob/master/day08-%E5%93%81%E7%89%8C%E7%AE%A1%E7%90%86/day08-%E5%93%81%E7%89%8C%E7%AE%A1%E7%90%86.md#14%E6%96%B0%E5%A2%9E%E5%AE%8C%E6%88%90%E5%90%8E%E5%85%B3%E9%97%AD%E7%AA%97%E5%8F%A3

## Zuul的路由过滤
https://github.com/coder-lzh/leyou/blob/master/day08-%E5%93%81%E7%89%8C%E7%AE%A1%E7%90%86/day08-%E5%93%81%E7%89%8C%E7%AE%A1%E7%90%86.md#224%E7%BB%95%E8%BF%87%E7%BD%91%E5%85%B3
注意一下：这个链接的方案是不对的。需要采取这种方法
比如说：http://api.leyou.com/api/item/brand/page   映射成   item-service/brand/page  
比如说：http://api.leyou.com/api/upload/image      映射成   upload-service/upload/image   
zuul:
  prefix: /api # 添加路由前缀
  retryable: true
  routes:
      item-service: /item/** # 将商品微服务映射到/item/**
      upload-service:       # 将上传微服务映不添加映射信息。注意，/api是映射，同样upload也是映射
        path: /upload/**
        serviceId: upload-service
        strip-prefix: false
