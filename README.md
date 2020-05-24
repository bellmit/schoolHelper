## 一、技术简介：

1.登陆注册功能：
	i:采用jwt+RAS(非对称加密算法)鉴权认证技术。性能与亮点：a:采用jwt无状态登陆，减小了服务端存储压力,客户端请求不依赖服务端的信息，任何多次请求不需要必须访问到同一台服务。b:采用RAS算法，同时生成两把密钥：私钥和公钥，私钥保存在授权中心，公钥保存在Zuul和各个微服务，这样请求到达微服务，微服务就可直接用公钥解析JWT，获取用户信息，无需访问授权中心。
	ii:采用阿里云短信技术+rabbitmq消息组件。性能与亮点：提高了安全性，另外，因为短信发送API调用时长的不确定性，短信发送采用异步发送方式，短信服务监听MQ消息，收到消息后发送短信，其它服务要发送短信时，通过MQ通知短信微服务，提高程序的响应速度
	iii:采用人脸识别登陆。性能与亮点：便捷，提高安全性
2.支付订单功能：
	i:采用阿里支付宝沙箱测试+花生壳内网穿透--支付回调
3.购物车功能：
	i:采用redis+localstorage。性能与亮点：实现了登陆与未登录不同状态下的购物车功能
4.搜索功能
	i:采用Elasticsearch全文检索技术。性能与亮点：提高了大数据量下搜索性能，大大提高了搜索速度。非mysql关系型数据库下的查询能比。
5.客服功能：
	i:采用腾讯QQ客服技术
5.校园服务：
	i:采用百度地图技术。将相关发布查询与地图结合，用户发布事件能在地图对应位置进行显示，更加便捷
6.智能服务：
	i:采用百度提供工具训练模型库，实现天气查询+疫情查询+垃圾分类等
7.新闻栏目：
	i:采用webmagic爬虫+定时任务技术。性能亮点：实现了定时抓取学校最新消息

## 二、项目简介：

《基于人工智能的智慧校园助手》，是一款旨在为同城高校的学子提供一个集电商、校园服务、同学互动等的智慧平台，为同城高校间学子提供便捷服务。
     该平台提供校园服务、校园商城、二手交易、智能问答四个大板块的服务。可有效为同学们提供物品遗失找回、校园活动发布及宣传、校园跑腿代购等，使同学们可以体验数字化校园的便捷；同时也满足在校大学生开店创业的需求，平台提供了商铺入驻的功能，大学生可以通过商铺入驻实现出售商品，实现B2C小型映射关系；我们还推出了二手交易功能，实现二手闲置物品的有效利用；最后我们还提供智能服务——基于人工智能的机器人，它提供了疫情实时查询，天气查询，垃圾分类信息查询等自动问答服务，用户可以根据自己的需求进行选择，对日常需要的信息进行整合，为用户提供了便利的服务。