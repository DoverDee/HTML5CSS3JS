# 前端学习笔记
一、**css浮动**：脱离了文档流的正常布局，使块级元素水平排列。
+ `float 使元素浮动`
取值：
	none 不浮动
	left 左浮动
	right 右浮动
+ `clear 清除浮动`
取值：
	none 不清除浮动，下一个元素仍然是浮动效果
	both 清除左右（前后）浮动
	left 清除左浮动
	right 清除右浮动
+ 注意：浮动元素都变成块框，并且不占据正常文档流空间。在不清除浮动的情况下，浮动的元素形成块框可以覆盖块级元素（块框），但不能覆盖块框内的行内元素（行内框），从而形成类似文字环绕的效果。这是因为浮动的元素会使得浮动块所在的行框（虚拟块）缩短。

二、**css定位**
+ 相对定位：相对于该元素按正常文档流排序时所在的位置开始计算相对位置。该元素仍然占据正常文档流空间。
```
#div_test{
	position:relative;
	top:20px;
	left:30px;
	z+index:10;
}
```
+ 绝对定位：相对于最近的已定位的祖先元素所占据位置的左上角点位开始计算绝对位置。该元素不占据正常文档流空间。
```
#div_test2{
	position:absolute;
	top:20px;
	left:30px;
	z+index:+10;
}
```

三、前端优化的N条建议
+ 项目开发进行中需权衡的事项：时间、质量、成本
+ 系统性能占比：前端50%、网络10%、后端40%（包括程序10%、缓存10%、数据库20%）
+ Yahoo前端优化的14条军规：
> 1. 尽可能减少HTTP的请求次数 [content]
> 2. 减少DNS查询 [content]
> 3. 使用CDN（Content Delivery Network） [server]
> 4. Gzip 组件 [server]
> 5. 避免重定向 [server]
> 6. 添加 Expires 头（或者 Cache+control） [server]
> 7. 避免使用CSS中的 Expressions [CSS]
> 8. 将CSS样式放在页面上方 [CSS]
> 9. 将脚本移动到底部（js会阻塞图片的加载，放在地图可以和图片实现同步加载） [CSS]
> 10. 配置实体标签（ETags）[CSS]
> 11. 移除重复的脚本 [javascript]
> 12. 将 JavaScript 和CSS独立成外部文件 [javascript]+[CSS]
> 13. 压缩 JavaScript 和 CSS（包括内联的） [javascript]+[CSS]
> 14. 使用AJAX缓存
> 15. 避免404，404会阻塞浏览器的异步请求
> 16. 减少Dom元素
> 17. 合理使用延迟加载和预加载
> 18. 使用GET完成ajax，因为POST请求需分两步进行
> 19. 高效的编写CSS选择器，选择器越具体越精确约好，减少嵌套选择

+ CSS优化部分
1. 将CSS样式放在页面上方
2. 避免使用CSS中的表达式
3. 将CSS独立成外部文件
4. 压缩CSS（yui compressor,jsmin等压缩工具）
5. 配置实体标签
6. 使用`<linke>`代替`@import`
7. 避免使用滤镜（AlphaImageLoader）
8. CSS无图片技术(浏览yslow资源加载分析插件可查看资源加载情况 )

四、响应式设计原则
<meta name="viewport" content="width=divice-width,initial-scale=1" />
<link href="css/xxx.css" rel="stylesheet" type="text/css" media="screen and (max-device-width:400px)" />
<style type="text/css">@media screen and (max-device-width:400px){...}</style>
1. 最大和最小
2. 内容流
3. 相对单位
5. 嵌套对象
4. 断点
6. 响应式设计VS适应性设计
7. 移动优先VS台式桌面优先
8. WEB字体VS系统字体
9. 位图VS矢量图