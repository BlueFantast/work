项目名称:优购商城

参考链接:http://www.jsdaima.com/Uploads/webpage/201706/1498177989/index.html

项目页面结构:

	首页
		顶部通栏
					所在城市,显示应用名,搜索图标
		轮播图
					展示商户促销信息图片
		功能导航(九宫格)
					展示站点的功能类目
		分类展示(图文信息)
					展示商品的类别,及主要促销信息
		回到顶部

	分类
		顶部通栏
					显示返回按钮,应用名,回到主页
		搜索栏
					用于搜索商品
		商品分类表(九宫格展示)
					用于展示所有分类信息(图文展示)	
	
	清仓
		顶部通栏
					显示返回按钮,应用名,回到主页
		轮播图
					展示热门打折信息
		清仓商品列表
					展示清仓商品列表(媒体组件)

	购物车
		顶部通栏
					显示返回按钮,应用名,回到主页
		已经选购商品列表
					展示已经购买的商品列表(媒体组件)
		底部统计结算
					显示已经购买商品的总价格,结算按钮

	我的
		个人中心
					显示用户头像,用户名,钱包,卡券,优购币信息,包含登录功能
		订单管理
					含待付款,待发货,待收货,待评价,退货和售后功能
		账户管理
					含账户余额,我的积分,我的礼券,我的收藏功能
		收货地址管理
					跳转到收获地址页面		
		设置
					跳转到设置页面	
		客服
					跳转到客服页面	
		帮助和反馈
					跳转到帮助和反馈页面


实现项目的技术

		mui,zepto,swiper,h5,css3,sass自己封装的各个js/css模块


项目代码结构

		
页面中使用的单位

		px	    : 定高部分用px
		rem		: 根据屏幕大小自适应的内容用rem
		百分比	: 容器宽度用百分比


手机相关统计数据(百度统计6月份数据)

		操作系统
			ios:  		ios10.3 	45% , ios10.2 		15% , ios9.3 	  11% , ios10.1 	 5%	
						ios10.0 	5% 	, ios9.2 		3%  , ios8.1	  3%  , ios8.4       3% 
						ios8.3 	 	2%
			android:	android5.1  32% , android6.0    25% , android4.4  20% , android5.0 	 8%
						android7 	7%  , android4.2    4%  , android4.3  3%  , android4.1   1%						
		分辨率
			ios:		750*1334	36% , 1242*2208		28%	, 640*1136	  16%
						2048*1536	5%	, 1125*2001		4%  , 640*960	  3%
			android:	1080*1920	31% , 720*1280		28% , 480*854	  6%
						540*960		6%  , 720*1184		5%  , 1080*1812	  5%


优化

		移出顶部和底部公共样式


问题汇总

		重复添加页面声明标签
		重复导入库文件
		mui中的a标签点击无跳转,用js从新绑定点击事件
		a标签点击时背景变灰,从新设置点击时a标签的样式
		链接跳转错误,从新设置index页面以外个页面的链接的相对路径

		
		用requirejs加载zepto不成功
		解决方法:
		shim: {
        	zepto: {
            	exports: '$'
        	},
        	event: {
            	des: ["zepto"],
				exports: '$'
        	}
    	}
		用requirejs加载css
		解决方法:
		1.下载插件require-css,放入main.js同目录下
		2.初始化模组,每一个模块加载前,判断是否需要加载css
		map: {
        	'*': {
            	'css': './lib/css.min'
        	}
   		},
		3.设置依赖,加载mui前先加载mui.min.css
		shim: {
        	'mui': {
            	deps: ['css!../statics/mui/css/mui.min.css']
        	}
		}
		

		模块化改造后页面出现闪顿
		解决方法:
		将ui库放在首页中提前加载


