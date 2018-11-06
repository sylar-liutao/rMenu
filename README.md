此组件为 rmenu 组件，基于vue封装的右键菜单组件，目前已上传npm和git，可直接安装/下载使用。
如有其他需求，请联系作者进行扩展和修改。
-----------------------------------------------------------------------------

#  1.安装
```
npm i rmenu
```
#  2.用法

main.js 中进行导入和使用：  
```
import rMenu from 'rmenu'  
Vue.use(rMenu);  
```
	
App.vue 对应页面中，直接使用，方式如下：  
```
<r-menu
	:liClick="rMenuClick"
	ref="rMenu"
	>
</r-menu>
```
#  3.参数说明

|参数|类型|是否必须|默认值|说明|
|:---|:---|:---|:---|:---|
|liClick|Function|否|无|菜单点击回调方法|
|ref|String|否|无|指定组件名称，方便在需要的时候调用树组件暴露的API方法|

#  4.回调说明

###  a.菜单点击回调方法  

liClick(菜单li对象)  // 组件会返回点击的菜单项，使用者需自行开发点击后的事件处理

#  5.数据源

|参数|类型|是否必须|默认值|说明|
|:---|:---|:---|:---|:---|
|x|Number|是|无|菜单left|
|y|Number|是|无|菜单top|
|data|Array|是|无|菜单对象数组[{option:'操作区分', optionName:'显示的操作名' }]|

#  6.API

*调用API的方法*  
**this.$refs.组件名称.API方法名(参数1,参数2...)**

###  a.打开菜单 openMenu
**参数**  

Object: { x:0, y:0, data: [] }

**返回**  

无

例：
```
this.$refs.rMenu.openMenu({
	y:100,
	x:100,
	data:[{
			optionName:"全部展开",
			option:'expand'
		},{
			optionName:"全部收起",
			option:'close'
		}
	]
})
```

###  b.关闭右键菜单 closeMenu
**参数**  

无

**返回**  

无


	