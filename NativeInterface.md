# 汽车人Native接口



 
### 调用方式
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

### 接口定义
####[autobots://testrn/getUrlParams]
获取原生参数 

``` javascript
	//传递参数
	无
	//返回值
	returnObject:"xxx"//直接返回字符串
	
```

####[autobots://testrn/getEmpCode]
获取当前登录人信息
``` javascript
	//传递参数
	无
	//返回值
	returnObject:{"empCode":"4576","empName":"吴潜"}
	
```

####[autobots://testrn/gotoHomePage]
返回汽车人首页 
``` javascript
	//传递参数
	无
	//返回值
	returnObject:null	
	
```
####[autobots://testrn/getUserLocation]
返回定位信息  
``` javascript
	//传递参数
	无
	//返回值
	returnObject:{"lng":"xxx","lat":"xxx"}	
	//lng-经度 lat-纬度
	
```

####[autobots://testrn/callDeviceShake]
开启摇一摇 
``` javascript
	//传递参数
	enabled=true
	//返回值
	returnObject:null
	
```

####[autobots://testrn/callDeviceShake]
关闭摇一摇 
``` javascript
	//传递参数
	enabled=false
	//返回值
	returnObject:null
```

####[autobots://testrn/callSinglePersonSelect]
选择员工(单选) 
``` javascript
	//传递参数
	title=选择员工&fection=最近选择员工
	//返回值
	returnObject:{"empCode":"4576","empName":"吴潜","empDept":"信息系统组"}
    //通知接收名称
    react_event_callSinglePersonSelect

```

####[autobots://testrn/callMultPersonSelect]
选择员工(多选)  
``` javascript
	//传递参数
	title=选择员工&fection=最近选择员工
	//返回值
	returnObject:[
		{"empCode":"4576","empName":"吴潜","empDept":"信息系统组"}
    ]
    //通知接收名称
    react_event_callMultPersonSelect

```


####[autobots://testrn/MultImagePicker]
> 选择图库(多选)  
``` javascript
	//传递参数
	无
	//返回值
	returnObject:["url","url","url"] //图片路径数组
    //通知接收名称
    react_event_multImagePicker

```

####[autobots://testrn/SingleImagePicker]
> 选择图库(单选)  
``` javascript
	//传递参数
	无
	//返回值
	returnObject:"url" //图片路径
    //通知接收名称
    react_event_singleImagePicker

```

####[autobots://testrn/CameraPicker]
> 拍照  
``` javascript
	//传递参数
	无
	//返回值
	returnObject:"url" //图片路径
    //通知接收名称
    react_event_cameraPicker

```


