# Mue-Snippet


## 目录
[TOC]

---
## 简介

Mue-Snippet 是mue提供的快速书写代码提示插件，在Sublime,Atom,VSCode, APICloud Studio2 ,Webstorm中集成mue控件及方法的代码提示，为快速开发助力. 里面封装了控件的常用参数及常用方法的语法补全, 版本对应 mue的版本.
> 1.3.1版本新增 控件名加"-demo" 快速生成控件初始化及结构,只要把结构复制到body对应的位置就行.

| **描述**            | **修改日期**            |
|:-------------------|-------------------:|
| 新增 ue-icon等相关布局     | 2018-11-12     |
| 新增 mue-store 初始化, b- 开头结构     | 2019-1-17     |

---
## 安装

方法1:
在应用市场输入 `mue-snippet` , 安装即可.

方法2: 
使用快捷键 mac: `command + shift + p` , windows: `ctrl + shift + p`;
- 输入`Install from VSIX`, 回车 ;
找到 `mue-Fast-Snippet-Vscode/mue-fast-0.0.1.vsix` 文件安装即可, 再按提示reload. 


---
## 简单使用示例

html触发结构代码片段的指令格式为: 'ue-控件名'，之后点击<kbd>Tab</kbd>键即可进行补全
JS触发代码片段的指令格式为： 'mue-控件名'，之后点击<kbd>Tab</kbd>键即可进行补全

**注意:** 生成代码后, 按<kbd>Tab</kbd>会定位在常用的编辑区域, 如果要写另外的控件代码, 要先按 <kbd>Esc</kbd> 再重复之前操作.

#### HTML 快速生成mue控件结构
(在body里面书写)
__ue-accordion__ <kbd>Tab</kbd> ( 生成折叠菜单结构 )

```html
<dl id="uiAccordion" class="mue-accordion">
  <dt class="mue-btn mue-box">
      <div class="span1"><!--折叠菜单--></div>
      <i class="icon-accordion"></i>
  </dt>
  <dd>
      <!--折叠菜单内容-->
  </dd>
</dl>
```

<strong class="hint">**注意**</strong>:如果忘记控件的名字, 输入<strong style="color:red;"> &lt;ue-</strong> 会有提醒相关的控件 ( <strong style="color:red;">生成的结构记得删掉第一个 &lt; </strong> ).


### JS 快速生成mue控件初始化
(在script里面书写)

__mue-accordion__ <kbd>Tab</kbd>  

```js
var uiAccordion = mue.accordion({
  id:"#uiAccordion"
});

```


### JS 快速生成完整demo  ( 推荐, 1.3.0 新增 )
(在script里面书写)

__mue-list-demo__ <kbd>Tab</kbd>  ( 生成list控件的初始化跟html结构 )

需要把html结构剪切到对应的位置去. 更多demo 请查看底部的控件列表

```
// 列表控件 js 初始化: 

var uiList = mue.list({
  id: "#uiList",
  url: "",
  data: {},             // 数据请求带过去的参数,分页在field配置
  template: listTemplate,
  field: {
      page: "page",     // 分页参数名
      size: "pageSize", // 分页大小参数名
      data: ""          // 数据字段名
  }
});
// 列表模板
function listTemplate (data) {
  var html = "";
  $.each(data,function(index, el) {
      html += '<li class="mue-btn" href="index.html"><i class="icon-facefill"></i>'+el.name+'</li>';
  });

  return html;
}

// 列表控件 html 对应的结构: 

<div id="uiList" class="mue-scroll">
  <div class="mue-scroll-head"></div>
  <div class="mue-scroll-main">
      <ul class="mue-list">
      </ul>
  </div>
  <div class="mue-scroll-foot"></div>
</div>

```

### JS 快速生成mue常用方法
(在script里面书写)

__mue-ajax__ <kbd>Tab</kbd> ( 生成请求的方法 )

```js
mue.ajax({
    url: "http://",
    data: {},//接口请求的参数

    // 可选参数
    method: "GET",
    timeout: 20000
}).done(function(result){
    
}).fail(function(result){
    
});
```

---



## mue JS方法及控件缩写

JS触发代码片段的指令格式为： 'mue-控件名'，之后点击<kbd>Tab</kbd>键即可进行补全

#### 控件简单初始化

控件名: mue.accordion 
我们只需要输入 __mue-accordion-demo__ <kbd>Tab</kbd> 就会生成完整的示例

### 控件完整demo缩写一览 (推荐 1.3.0新增)

| **缩写代码**   | **描述**            |
|:------------- |:-------------------|
| mue-accordion-demo  | 折叠菜单完整示例       |
| mue-actionsheet-demo  | 上拉菜单完整示例       |
| mue-dialog-demo  | 弹出框完整示例       |
| mue-dropdown-demo  | 下拉菜单完整示例       |
| mue-list-demo  | 列表侧滑完整示例       |
| mue-listview-demo  | 列表侧滑完整示例       |
| mue-listview-demo-custom  | 列表侧滑静态完整示例       |
| mue-pullrefresh-demo  | 下拉刷新完整示例       |
| mue-scroll-demo  | 滚动控件完整示例       |
| mue-number-demo  | 数字条完整示例       |
| mue-pickerdate-demo  | 日期完整示例       |
| mue-rating-demo  | 星级评分完整示例       |
| mue-scroll-demo  | 滚动控件完整示例       |
| mue-sidebar-demo  | 滚动控件完整示例       |
| mue-slide-demo  | 焦点图滑动完整示例       |
| mue-tab-demo  | Tab控件-示例  |
| mue-tab-demo-footer  | Tab控件菜单在底部滚动-示例  |
| mue-swipe-demo  | 抽屉菜单完整示例       |
| mue-levelselect-demo  | 级联菜单完整示例       |
| mue-input-demo  | 输入框完整示例       |
| mue-searchbar-demo  | 搜索完整示例       |
| mue-select-demo  | 选择列表完整示例       |
| mue-stepbar-demo  | 步骤条完整示例       |
| mue-upload-demo  | 上传完整示例       |
| mue-floor-demo<span style="color:red">新</span>  | 楼层完整demo       |

控件名: mue.accordion 
我们只需要输入 __mue-accordion__ <kbd>Tab</kbd> 就会生成最简单的初始化脚本


| **缩写代码**   | **描述**            |
|:------------- |:-------------------|
| mue-accordion  | 折叠菜单初始化       |
| mue-actionsheet  | 上拉菜单初始化       |
| mue-dialog  | 弹出框初始化       |
| mue-dropdown  | 下拉菜单初始化       |
| mue-list  | 列表初始化       |
| mue-listview  | 列表侧滑初始化       |
| mue-pullrefresh  | 下拉刷新初始化       |
| mue-scroll  | 滚动加载初始化       |
| mue-number  | 数字条初始化       |
| mue-pickerdate  | 日期初始化       |
| mue-rating  | 星级评分初始化       |
| mue-searchbar  | 搜索控件初始化       |
| mue-sidebar  | 滚动控件初始化       |
| mue-slide  | 滑动控件初始化       |
| mue-tab  | 滑动Tab控件初始化  |
| mue-swipe  | 抽屉菜单初始化       |
| mue-levelselect  | 级联菜单初始化       |
| mue-input  | 输入框初始化       |
| mue-searchbar  | 搜索初始化       |
| mue-select  | 选择列表初始化       |
| mue-stepbar  | 步骤条初始化       |
| mue-upload  | 上传初始化       |
| mue-router  | mue 单页初始化 |
| router-load  | 单页跳转 |
| router-refresh  | 单页刷新 |
| router-replace  | 单页替换 |
| router-back  | 单页后退 |
| router-getPageParams  | 获取页面参数 |
| router-loadPart  | 局部加载 |
| mue-store   | 数据行为存储器 |
| mue-store-demo   | 数据行为存储器 |
| loader-define  | 模块定义 |
| loader-require  | 模块加载 |
| loader-import  | 脚本及样式资源动态引入 |
| loader-map  | 单个模块配置 |
| loader-mapall  | 多个模块配置 |
| loader-delay  <span style="color:red">新</span> | 编译延迟组件 |
| loader-component  <span style="color:red">新</span> | 编译组件 |
| loader-view  <span style="color:red">新</span> | 编译模板 |
| loader-load  <span style="color:red">新</span> | 加载组件 |
| mue-timer   <span style="color:red">新</span> | 倒计时 |
| mue-page   <span style="color:red">新</span> | 插入页面 |
| mue-date-formate  <span style="color:red">新</span> | 日期格式化 |
| mue-date-convert  <span style="color:red">新</span> | 日期转对象 |
| mue-date-after  <span style="color:red">新</span> | 几天后 |
| mue-date-afterTime  <span style="color:red">新</span> | 几小时后 |
| mue-date-toWeek  <span style="color:red">新</span> | 日期转星期 |
| mue-history-get  <span style="color:red">新</span> | 获取历史记录 |
| mue-history-getLast  <span style="color:red">新</span> | 获取最后一条历史记录 |
| mue-history-getParams  <span style="color:red">新</span> | 获取通用传参,支持多种类型 |
| mue-history-getParams  <span style="color:red">新</span> | 获取通用传参,支持多种类型 |
| mue-history-check  <span style="color:red">新</span> | 检测路由页面有没有加载 |
| mue-history-checkComponent  <span style="color:red">新</span> | 检测组件有没有加载 |
| mue-history-refresh  <span style="color:red">新</span> | 刷新 |


## mue HTML结构缩写一览

html触发结构代码片段的指令格式为: 'ue-控件名'，之后点击<kbd>Tab</kbd>键即可进行补全



### 控件结构缩写

| **缩写代码**   | **描述**            |
|:------------- |:-------------------|
| ue-accordion  | 折叠菜单结构       |
| ue-actionsheet  | 上拉菜单结构       |
| ue-dialog  | 弹出框结构       |
| ue-dropdown  | 下拉菜单结构       |
| ue-listview  | 列表侧滑结构       |
| ue-listview-custom  | 列表侧滑静态结构       |
| ue-number  | 数字条结构       |
| ue-pickerdate  | 日期结构       |
| ue-rating  | 星级评分结构       |
| ue-list  | 列表滚动控件结构       |
| ue-scroll  | 滚动控件结构       |
| ue-sidebar  | 滚动控件结构       |
| ue-slide  | 滑动控件结构       |
| ue-slide-tab  | 滑动Tab控件结构  |
| ue-swipe  | 抽屉菜单结构       |
| ue-searchbar  | 搜索结构       |
| ue-range  | 滑动条结构       |
| ue-switch  | 切换按钮结构       |
| ue-select  | 选择列表结构       |
| ue-stepbar  | 步骤条结构       |
| ue-btn             | 按钮                         |
| ue-levelselect  <span style="color:red">新</span>| 级联控件结构       |
| ue-tab  <span style="color:red">新</span>| 选项卡结构       |
| ue-upload  <span style="color:red">新</span>| 上传结构       |
| ue-input | 输入框                                    |  
| ue-floor | 楼层结构                                    |  

### 页面结构缩写

| **缩写代码**   | **描述**            |
|:------------- |:-------------------|
| ue-router  <span style="color:red">新</span>     | mue 单页标准结构    |
| ue-html       | mue HTML标准结构    |
| ue-page       | mue 页面标准结构    |
| ue-header        | 生成header结构        |
| ue-header-side   | 生成header左对齐结构   |
| ue-panel      | panel结构          |
| ue-table      | 表格结构            |
| ue-form       | 表单结构            |
| ue-form-edit  | 表单填写结构        |
| ue-form-submit| 表单底部结构        |
| ue-nav | 导航菜单        |
| ue-nav-icon | 导航菜单带图标        |
| ue-list-arrow  | 箭头列表结构       |
| ue-list-checkbox  | 多选列表结构       |
| ue-list-radio  | 单选列表结构       |
| ue-list-group  | 分组列表结构       |
| ue-list-icon  | 图标列表结构       |
| ue-list-photo  | 图片列表结构       |
| ue-list-thumbnail  | 列表多行带缩略图结构       |
| ue-icon  | 图标       |
| ue-icon-bg  | 背景图标       |
| ue-icon-grid  | 九宫格图标结构       |
| ue-icon-round  | 九宫格背景图标结构       |
| ue-icon-img  | 九宫格图标图片类结构       |
| ue-hint  | 静态提醒       |
| ue-tag  | 标签类       |
| ue-sub  | 角标       |
| ue-badges  | 红点提醒       |


### 布局结构缩写

| **缩写代码**   | **描述**            |
|:------------- |:-------------------|
| ue-box        | 弹性布局结构       |
| ue-box-space  | 弹性布局留白结构    |
| ue-box-center  | 块元素水平垂直居中结构    |
| ue-fluid      | 百分比布局结构      |
| ue-fluid-space| 百分比留白布局结构    |
| ue-fluid-5    | 5列布局结构        |


### 表单元素结构缩写

| **缩写代码**        | **描述**                      |
|:-------------      |:-------------------          |
| ue-radio           | 单选框                        |
| ue-checkbox        | 多选框                        |
| ue-checkbox-custom | 多选框自定义结构,便于修改样式    |
| ue-choose | 单选多选的不同样式                       |
| ue-switch | 开关切换                                  |
| ue-range | 拖动条                                    |
| ue-progress  | 进度条结构       |
| ue-check  <span style="color:red">新</span>| 选择按钮结构       |


### 新增结合数据驱动的标签, 1.6.x 从 `b-text` 改成 `ue-b-text`

| **缩写代码**        | **描述**                      |
|:-------------      |:-------------------          |
| ue-b-text          | 设置文本                        |
| ue-b-html        | 设置html                        |
| ue-b-value | 设置value    |
| ue-b-show  |  显示当前dom  |
| ue-b-model  |  双向绑定  |
| ue-b-bind  |  设置属性  |
| ue-b-style  |  设置style的样式  |
| ue-b-class  |  设置class的样式  |
| ue-b-template  |  绑定模板  |
| ue-b-click  |  点击事件  |