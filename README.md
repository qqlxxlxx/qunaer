# qunaer

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).


## 使用技术
Vue + Vue Router + Vuex + axios + stylus + webpack


## 实现功能
* 前进刷新、后退缓存用户浏览位置和浏览数据
* 首页轮播、导航按钮的分页
* 城市选择切换、城市搜索切换
* 详情页图片展示


## 问题总结
#### 在手机QQ浏览器上，详情页头部不能随页面滚动而显示/隐藏
原因是获取网页滚动距离未作兼容处理，解决方法如下
谷歌支持的方式：`document.body.scrollTop`
ie和火狐支持的方式：`document.documentElement.scrollTop`
高版本浏览器支持的：`window.pageYOffset`

#### 引入better-scroll的组件中使用@click事件需要注意的问题
在移动端，引入better-scroll的组件中使用@click事件的时候，better-scroll的配置中没有设置click：true，点击事件失效

#### touchstart和click事件冲突
这两个事件如果同时使用的时候，可能会引发冲突，即touchstart好使，click失效，这个问题来自于touchstart下阻止了默认事件，导致click失效。需要阻止touchstart事件扩散和拦截默认事件，在移动端使用只使用touchstart
`@touchstart.stop.prevent="handleTouchStart"`
