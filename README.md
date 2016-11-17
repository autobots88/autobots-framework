# RN开发框架说明





## 组件

### Nav
> 使用导航器可以让你在应用的不同场景（页面）间进行切换。导航器通过路由对象来分辨不同的场景。  
 

#### 调用方式
``` javascript
  import {Nav} from 'autobots-framework';
  import HomePage from './pages/HomePage';
  
  Nav.pop();//返回上一页面
  
  //跳转至页面
  Nav.push({
              name: 'HomePage', 
              component: HomePage,
              params: {
              }
        });
  //你也可以调用Nav.navigator对象来使用RN的完整路由功能
  Nav.navigator.popToTop()
  ...
  //更多可查看RN帮助文档
```

### Native
> 提供RN与原生交互功能。  
 
#### 调用方式
``` javascript
  import {Native} from 'autobots-framework';
  //回到汽车人首页
  Native.gotoHomePage();
  
  //...后续回有更多接口加入
   
```

### Http
> 通用网络请求。  
 
#### 调用方式
``` javascript
import {Http} from 'autobots-framework';
  
Http.request("http://xxx.com{name:""}).then(function(data){
          if(data)
          {
	          //成功
	          ...
          }else
          {
	          //失败
	          ...
          }
      });

   
```


### Components
> 包含一些基础RN组件。  
 
#### Navbar
``` javascript
  import {Components} from 'autobots-framework';
  const {Navbar} = Components;
  
  ...
  render(){
	return(<Navbar title="xxx" onLeftButtonPress={()=>{
		  //左侧返回按钮点击事件
          ...
      }}  />)
  }
  ...
   
```

### Config
> 提供系统内的一些配置参数。  
 
#### 调用方式
``` javascript
  import {Config} from 'autobots-framework';
  //获取参数对象
  var c = Config.get();
  
  console.log(c);
  //输出结果
   {
	  name:"xxx",
	  homeTitle:"xxx", 
	  startApp:object,//首页对象
	  empCode:"xxx",//当前登录人工号
	  urlParams:"xxx",//从原生获取的网页传递参数
	}
   
```


### Toast
> toast功能。  
 
#### 调用方式
``` javascript
  import {Toast} from 'autobots-framework';
  //短文本
  Toast.Show('xxx');
  //超长文本
  Toast.ShowLong('xxx');

```

### 复选框

使用 `- [ ]` 和 `- [x]` 语法可以创建复选框，实现 todo-list 等功能。例如：

- [x] 已完成事项
- [ ] 待办事项1
- [ ] 待办事项2

> **注意：**目前支持尚不完全，在印象笔记中勾选复选框是无效、不能同步的，所以必须在**马克飞象**中修改 Markdown 原文才可生效。下个版本将会全面支持。


## 印象笔记相关

### 笔记本和标签
**马克飞象**增加了`@(笔记本)[标签A|标签B]`语法, 以选择笔记本和添加标签。 **绑定账号后**， 输入`(`自动会出现笔记本列表，请从中选择。

### 笔记标题
**马克飞象**会自动使用文档内出现的第一个标题作为笔记标题。例如本文，就是第一行的 `欢迎使用马克飞象`。

### 快捷编辑
保存在印象笔记中的笔记，右上角会有一个红色的编辑按钮，点击后会回到**马克飞象**中打开并编辑该笔记。
>**注意：**目前用户在印象笔记中单方面做的任何修改，马克飞象是无法自动感知和更新的。所以请务必回到马克飞象编辑。

### 数据同步
**马克飞象**通过**将Markdown原文以隐藏内容保存在笔记中**的精妙设计，实现了对Markdown的存储和再次编辑。既解决了其他产品只是单向导出HTML的单薄，又规避了服务端存储Markdown带来的隐私安全问题。这样，服务端仅作为对印象笔记 API调用和数据转换之用。

 >**隐私声明：用户所有的笔记数据，均保存在印象笔记中。马克飞象不存储用户的任何笔记数据。**

### 离线存储
**马克飞象**使用浏览器离线存储将内容实时保存在本地，不必担心网络断掉或浏览器崩溃。为了节省空间和避免冲突，已同步至印象笔记并且不再修改的笔记将删除部分本地缓存，不过依然可以随时通过`文档管理`打开。

> **注意：**虽然浏览器存储大部分时候都比较可靠，但印象笔记作为专业云存储，更值得信赖。以防万一，**请务必经常及时同步到印象笔记**。

## 编辑器相关
### 设置
右侧系统菜单（快捷键`Cmd + M`）的`设置`中，提供了界面字体、字号、自定义CSS、vim/emacs 键盘模式等高级选项。

### 快捷键

帮助    `Cmd + /`
同步文档    `Cmd + S`
创建文档    `Cmd + Opt + N`
最大化编辑器    `Cmd + Enter`
预览文档 `Cmd + Opt + Enter`
文档管理    `Cmd + O`
系统菜单    `Cmd + M` 

加粗    `Cmd + B`
插入图片    `Cmd + G`
插入链接    `Cmd + L`
提升标题    `Cmd + H`

## 关于收费

**马克飞象**为新用户提供 10 天的试用期，试用期过后需要[续费](maxiang.info/vip.html)才能继续使用。未购买或者未及时续费，将不能同步新的笔记。之前保存过的笔记依然可以编辑。


## 反馈与建议
- 微博：[@马克飞象](http://weibo.com/u/2788354117)，[@GGock](http://weibo.com/ggock "开发者个人账号")
- 邮箱：<hustgock@gmail.com>

---------
感谢阅读这份帮助文档。请点击右上角，绑定印象笔记账号，开启全新的记录与分享体验吧。




[^demo]: 这是一个示例脚注。请查阅 [MultiMarkdown 文档](https://github.com/fletcher/MultiMarkdown/wiki/MultiMarkdown-Syntax-Guide#footnotes) 关于脚注的说明。 **限制：** 印象笔记的笔记内容使用 [ENML][5] 格式，基于 HTML，但是不支持某些标签和属性，例如id，这就导致`脚注`和`TOC`无法正常点击。


  [1]: http://maxiang.info/client_zh
  [2]: https://chrome.google.com/webstore/detail/kidnkfckhbdkfgbicccmdggmpgogehop
  [3]: http://adrai.github.io/flowchart.js/
  [4]: http://bramp.github.io/js-sequence-diagrams/
  [5]: https://dev.yinxiang.com/doc/articles/enml.php


