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
  
Http.request("http://xxx.com",{name:""}).then(function(data){
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

#### ImagesPicker
``` javascript
  import {Components} from 'autobots-framework';
  const {ImagesPicker} = Components;
  
  ...
  <ImagesPicker ref={imgPicker=>this.imgPicker=imgPicker} onPicked={(data)=>{
		   //返回值
			  单选返回图片url
			  多选返回图片url数组
 }} />

 this.imgPicker.MutiPick(); //多选
 this.imgPicker.SinglePick(); //单选
 ...
   
```


#### CameraPicker
``` javascript
  import {Components} from 'autobots-framework';
  const {CameraPicker} = Components;
  
  ...
  <CameraPicker ref={caPicker=>this.caPicker=caPicker} onPicked={(data)=>{
		   //返回值
		   返回图片url
 }} />

 this.caPicker.Pick(); //拍照


 ...
   
```

#### EmployeePicker
``` javascript
  import {Components} from 'autobots-framework';
  const {EmployeePicker} = Components;
  
  ...
  <EmployeePicker ref={empPicker=>this.empPicker=empPicker} onPicked={(data)=>{
		   //返回值
		   返回图片url
 }} />

 this.empPicker.MutiPick("选择出差人","最近选择出差人"); //多选
 this.empPicker.SinglePick("选择出差人","最近选择出差人");//单选

 ...
   
```

#### Loading
> 调用汽车人统一loading。  

``` javascript
  import {Components} from 'autobots-framework';
  const {MainLoading} = Components;
  //短文本
  MainLoading.Show();
  //超长文本
  MainLoading.ShowLong();

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
	  employee:{empCode:"xxx",empName:"xxx"},//当前登录人信息	
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


