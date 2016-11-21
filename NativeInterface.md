### Native
> 提供RN与原生交互功能。  
 
#### 调用方式
``` javascript
  import {Native} from 'autobots-framework';
  //回到汽车人首页
  Native.gotoHomePage();
  
  //...后续回有更多接口加入
   
  //Native请求url格式
  //"autobots://{appcode}/{调用接口名称}+{参数}"
  //如调用选择员工接口
  //"autobots://testrn/callMultPersonSelect?title=选择被分享人&fection=最近选择被分享人"

  //Native请求返回Json格式
  {
	  "code":200,
	  "state":1, //0-失败 1-成功，-1 也是失败，但不会提示出错信息
	  "info":"", //返回结果信息，state为0时会在app端弹出显示
	  "returnObject":{
	  }  //接口返回数据
   }


```

#### 接口定义

> 获取原生参数 autobots://testrn/getUrlParams

``` javascript
	//传递参数
	无
	//返回值
	returnObject:"xxx"//直接返回字符串
	
```


> 获取当前登录人信息 autobots://testrn/getEmpCode 
``` javascript
	//传递参数
	无
	//返回值
	returnObject:{"empCode":"4576","empName":"吴潜"}
	
```

> 返回汽车人首页 autobots://testrn/gotoHomePage 
``` javascript
	//传递参数
	无
	//返回值
	returnObject:null	
```

> 返回定位信息 autobots://testrn/getUserLocation 
``` javascript
	//传递参数
	无
	//返回值
	returnObject:{"lng":"xxx","lat":"xxx"}	
	//lng-经度 lat-纬度
```

> 开启摇一摇 autobots://testrn/callDeviceShake 
``` javascript
	//传递参数
	enabled=true
	//返回值
	returnObject:null
```

> 关闭摇一摇 autobots://testrn/callDeviceShake 
``` javascript
	//传递参数
	enabled=false
	//返回值
	returnObject:null
```


> 选择员工(多选) autobots://testrn/callMultPersonSelect 
``` javascript
	//传递参数
	title=选择员工&fection=最近选择员工
	//返回值
	returnObject:[
		{"empCode":"4576","empName":"吴潜","empDept":"信息系统组"}
		...]
    //通知接收名称
    //react_event_callMultPersonSelect

```

> 选择员工(单选) autobots://testrn/callSinglePersonSelect 
``` javascript
	//传递参数
	title=选择员工&fection=最近选择员工
	//返回值
	returnObject:{"empCode":"4576","empName":"吴潜","empDept":"信息系统组"}
    
    //通知接收名称
    react_event_callSinglePersonSelect

```
