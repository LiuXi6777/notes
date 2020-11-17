## 1.性能管理
- 尽可能的减少http的请求数
- 使用CDN(content delivery network)
- 添加 Expires 头( 或者 Cache-control )
- Gzip组件缓存技术
- 将css样式放在页面的上方
- 将脚本移动到底部（包括内联的）
- 避免在css中使用expressions
- 将 javascript 和 css 独立成外部文件。
- 减少dns查询
- 压缩JavaScript和css文件(包括内联的)
- 避免跳转redirect
- 移除重复的脚本
- 配置ETags
- 缓存ajax请求

## 2.JSON对象遍历
```
for (var key in Obj){

}
```
## 3.合并JSON对象的常见方式
1. 循环遍历法
2. Object.assign() 
3. 用JQuery插件





