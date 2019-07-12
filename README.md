# travel

通过使用Vue的一些基础功能实现 去哪儿网-旅游板块的部分功能 
主要涉及的知识: 
- 插值语法({{}})的使用;
- 指令: v-if进行条件渲染,
  v-for进行列表渲染
  v-model对输入框元素的值进行双向绑定，
  v-show控制组件显示和隐藏，
  v-bind(:)绑定属性，
  v-on（@）进行事件监听;
- 属性
  计算属性与侦听器属性的使用
- 生命周期钩子
  主要使用的钩子函数为created，mounted
- 组件的使用:
  父子组件的通信，
  父组件通过属性传递值，子组件通过props属性接收值，
  子组件通过$emit触发事件向父组件传递值，父组件通过监听事件接收值
  通过递归组件实现二级列表
- router的使用:
  动态路由的基本使用(传参)
  声明式导航(to属性)和编程式导航(通过js调用$router上的方法)的基本使用
  滚动行为的处理
- vuex的基本使用: 
  在到根实例上注册store选项，通过调用$store.state取到需要的值。
  通过提交 mutation去修改state中的值。
- axios
- 其他第三方库
  better-scroll 处理滚动区域的问题
  Swiper 轮播图的处理
  pinyin 将汉字转成拼音，为了(zhuang bi)解决的搜索的一些问题
  
> 注: 能力有限,开发过程使用的数据只有一小部分静态数据(效果和目的达到就行-_-)，存放在static/mock中，
  开发环境下proxyTable已经配置好了。同时配置了同局域网下手机可以通过ip+port访问
  
> 能点击的区域很少,目的达到就行-_-,
  (主页只有城市和热门推荐区域能点击,城市列表应该是功能最完善的,详情页只有banner区域和返回按钮可以点击了),
  毕竟主要目的是为了练习vue~,多多体谅！！！
  
  
## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
