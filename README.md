# 香哈微信小程序

> 基于 [wxapp](http://mp.weixin.qq.com/debug/wxadoc/dev/)原生+[wepy](https://tencent.github.io/wepy/)框架开发，用`wepy`打包

## 搭建项目步骤

### 1.准备工作
本机已经安装 [node.js](https://nodejs.org/en/) ; 如果没有安装请自行安装 ; 安装完成以后自带 `npm` 包 ; 国内的`npm`速度较慢 ; 可以外挂`淘宝镜像cnpm` 将下面的代码复制到命令行执行 ;
**npm install -g cnpm --registry=https://registry.npm.taobao.org** ;
本机也已经安装 [微信web开发者工具](https://mp.weixin.qq.com/debug/wxadoc/dev/devtools/download.html?t=201818)

### 2.开始项目搭建
在本项目的目录下

· **cnpm install wepy-cli -g** 安装(更新)wepy 命令行工具

· **cnpm install** 安装(更新)依赖包

· **wepy build --watch** 开发实时编译

· **wepy build --no-cache** 部署生产环境

· **wdtcompile** 编译服务号搜索展示页面(和上面实时编译同形)  需先安装npm install -g wdt-compiler


### 3.运行项目

使用微信开发者工具新建项目，选择本项目下的 `dist` 目录(dist目录是执行了编译后生成的目录;如果没有请执行`实时编译`命令 ; 开发时可以忽略 `dist` 的存在 ; 永远操作的是 `src` 里面的代码) ; 微信开发者工具 --> 详情 --> 关闭ES6转ES5 ; 关闭上传自动压缩(wepy已给压缩) 本地项目目录运行wepy build --watch ; 开启实时编译

## 项目结构 [src] 在开发过程中;只需要编译src中的文件即可查看效果

```bash


├── app.wpy                         // 入口文件
├── components                      // 组件
│   ├── common                      // 公共组件
│   │   ├── bottomBarTwo.wpy        // 页面快捷bar  (活动页面)
│   │   ├── bottomLoadMore.wpy      // 底部加载更多组件
│   │   ├── bottomText.wpy          // 底部语组件
│   │   ├── levitateActivity.wpy    // 悬浮活动按钮组件
│   │   ├── levitateShare.wpy       // 悬浮分享按钮组件
│   │   ├── newBottomBar.wpy        // 新收藏和分享bar组件
│   │   ├── payPop.wpy              // 支付弹窗组件
│   │   ├── placeholder.wpy         // 空列表显示组件
│   │   ├── qbBottomBar.wpy         // 底部收藏bar (QQ浏览器中使用)
│   │   ├── xhAdBox.wpy             // 香哈广告组件
│   │   ├── xhInfoSkeleton.wpy      // 香哈菜谱详情骨架屏占位组件
│   │   ├── xhListSkeleton.wpy      // 香哈列表骨架屏占位组件
│   │   └── xhSkeleton.wpy          // 香哈单个骨架屏占位组件
│   ├── menuComList.wpy             // 菜单列表组件(菜单列表使用)
│   ├── recipesComAList.wpy         // 菜谱A列表组件(菜谱详情相关菜谱 + 分享出去的收藏(oType=2))
│   ├── courseComList.wpy           // 课程列表组件(vip名厨)
│   ├── recipesComBList.wpy         // 菜谱B列表组件(首页本周佳作 + 菜单详情 + 三餐页面 + 视频菜谱列表)
│   └── searchBar.wpy               // 搜索组件
├── images                          // 图片文件夹
├── pages                           // 页面
│   ├── activityOne.wpy             // 年夜饭活动页面
│   ├── classify.wpy                // 分类页面
│   ├── collection.wpy              // 收藏页面
│   ├── collectionShare.wpy         // 分享出去的收藏页面
│   ├── home.wpy                    // 首页页面
│   ├── member.wpy                  // 会员页面
│   ├── menuDetail.wpy              // 菜单详情页面 (/pages/menuDetail?code=xxx)
│   ├── menuList.wpy                // 菜单列表页面
│   ├── recipeDetail.wpy            // 菜谱详情页面 (/pages/recipeDetail?dishCode=xxx)
│   ├── sancan.wpy                  // 三餐页面
│   ├── search.wpy                  // 搜索页面 (/pages/search?code=xxx)
│   ├── searchCaidan.wpy            // 搜索菜单页面
│   ├── user.wpy                    // 我的页面
│   ├── videoRecipesList.wpy        // 视频菜谱列表页面
│   └── vip.wpy                     // vip名厨页面
├── styles                          // 公共样式
│   └── base.less
└── utils                           // 工具类
    ├── tip.js                      // 提示弹框组件
    ├── util.js                     // 工具
    └── wxRequest.js                // 请求封装

```

## 技术栈:
> * wxapi ^x.x.x
> * wepy  ^1.5.7
> * less ^1.3.0
> * es6

## 开发注意
#### 默认背景图
因为小程序图片是使用 **image** 组件来完成的 ; 在给默认图的时候 **background: url(  )** 只可用网络图 ; 本地暂时不可以 ; 现给定3个网络图来适配大部分使用场景 ; 开发者可根据实际开发场景来选择使用即可~~~

· 600*300尺寸 https://s2.cdn.xiangha.com/images/m5/Common/echo.png  (现使用于列表中的大图 ; 本周佳作)

· 100*75尺寸 https://s2.cdn.xiangha.com/images/m5/Common/echo2.jpg  (现使用于列表中的小图 ; 搜索结果)

· 600*338尺寸 http://s2.cdn.xiangha.com/images/m5/Common/video-bg.png (现使用于菜谱详情头图)

· 5:3    尺寸 http://s2.cdn.xiangha.com/images/m5/Common/caidan-bg.png (现使用于菜单详情)

· 3:2    尺寸 http://s2.cdn.xiangha.com/images/m5/Common/step-bg.png    (现使用于步骤背景图)

------

## 版本迭代

#### 2018-01-25版本更新v2.0.0
  - 香哈小程序全新改版
  - 1、首页推荐模板
  - 2、VIP名厨课体系
  - 3、个人账号体系（收藏、浏览）
  - 4、微信支付
  - 5、分享、反馈客服

#### 2018-01-29版本更新v2.0.2
  - 1、登录、收藏列表刷新bug修复
  - 2、安卓UI调整
  - 3、分享策略调整
  - 4、年夜饭活动及推广

#### 2018-02-06版本更新v2.0.5
  - 1、活动页面的删除领奖记录
  - 2、三餐底部留白
  - 3、三餐标题一行省略打点
  - 4、vip 空内容判断
  - 5、活动页面添加底部bar

#### 2018-03-15版本更新v2.0.7
  - 1、页面层级由3改为4
  - 2、公众号倒流：详情页顶部banner、首页中部icon
  - 3、分享体验优化：
  - 4、引导添加桌面
  - 5、视频播放，网络状况判断
  - 6、细节UI调整：视频时长、用料、昵称样式等
  - 7、bug修复：分享、收藏（同类页面）

#### 2018-03-26版本更新v2.1.0
  - 1、QB接入小程序开发调整（首页、导航、详情页细节）
  - 2、三餐页面分享区分早中晚并准确识别
  - 3、名厨banner等图片拉伸bug修复
  - 4、搜索列表页formid 的收集
  - 5、菜谱详情页小贴士下方添加广告

#### 2018-04-16版本更新v2.1.2
  - 1、会员统计位置名称修改
  - 2、广告样式、多增广告位
  - 3、骨架屏策略，优化加载体验
  - 4、首页本季食材改为热门推荐，出分类数据
  - 5、分享图标动画优化&&部分UI
  - 6、开通会员文案服务端控制

#### 2018-06-12版本更新v2.1.5
  - 1、IOS开通会员优化
  - 2、注释重新进入登录授权
  - 3、支付弹层关闭按钮放大

#### 2018-06-14版本更新v2.1.7
  - 1、新增服务号搜索功能
  - 2、重新开启进入登录授权
  - 3、广告出现方式策略(来自服务号搜索不展示)
  - 4、IOS开通会员优化确定则关闭

#### 2018-06-15版本更新v2.2.0
 - 1、配合服务号搜索调整UI
 - 2、全部关闭支付

#### 2018-06-14版本更新v2.2.1
 - 1、开启安卓支付







