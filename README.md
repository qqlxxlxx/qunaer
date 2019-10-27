# qunaer
Vue + Vue Router + Vuex + axios + stylus + webpack

## Project setup
```
# install dependencies
npm install

# Compiles and hot-reloads for development
npm run serve

# Compiles and minifies for production
npm run build
```

## 实现功能
* 网页优化：前进刷新、后退缓存用户浏览位置和浏览数据
* 使用axios获取请求：为了效率，不能连续发送5个ajax请求，可以在父组件发送一个请求，为5个子组件获取数据
* 首页：轮播图、导航按钮的左右滑动效果、猜你喜欢组件开发、周末去哪儿组件开发
* 城市页：城市定位、城市列表渲染的点击选择效果、搜索框逻辑实现、Vuex管理共享城市、字母表滚动效果
* 详情页：头部返回及滑动动画、图片展示的画册效果


## 问题总结
#### 在手机QQ浏览器上，详情页头部不能随页面滚动而显示/隐藏
原因是获取网页滚动距离未作兼容处理，解决方法如下：
* 谷歌支持的方式：`document.body.scrollTop`
* ie和火狐支持的方式：`document.documentElement.scrollTop`
* 高版本浏览器支持的：`window.pageYOffset`


#### 引入better-scroll的组件中使用@click事件需要注意的问题
在移动端，引入better-scroll的组件中使用@click事件的时候，better-scroll的配置中没有设置click：true，点击事件失效


#### touchstart和click事件冲突
这两个事件如果同时使用的时候，可能会引发冲突，即touchstart好使，click失效，这个问题来自于touchstart下阻止了默认事件，导致click失效。需要阻止touchstart事件扩散和拦截默认事件，在移动端使用只使用touchstart。
`@touchstart.stop.prevent="handleTouchStart"`
