Google App Engine上安装鸟巢采集客户端应用
=========================

*   [注册Google账号](#signup)
*   [建立Google App Engine应用](#create)
*   [发布到Google App Engine](#deploy)
*   [添加客户端应用到鸟巢采集](#addapp)

* * *


<h2 id="signup">注册Google账号</h2>

<https://accounts.google.com/SignUp>

<h2 id="create">建立Google App Engine应用</h2>

<https://appengine.google.com>

![create_app2.jpg](/static/img/gae/create_app2.jpg)


<h2 id="deploy">发布到Google App Engine</h2>

1.下载 `GAE` 发布工具 `windows-gae-deploy-tools.zip` 
	
	解压 `windows-gae-deploy-tools.zip`

2.下载采集器应用包 `soso-crawler-gae.zip`

	解压 `soso-crawler-gae.zip` 到发布工具 `windows-gae-deploy-tools` 的 `war` 目录
	war目录结构如下:
	-war
		-WEB-INF
		-index.html
		-favicon.ico
	....

2.修改 `project-app-deploy.xml` 配置文件

	your.gae.app.id #Google App Engine 的App Id
	your.gae.account #Google App Engine 的账户
	your.gae.account.password #Google App Engine 的账户密码

3.双击运行 `deploy.bat` 进行发布

4.发布成功后，等待5到10分钟 `GAE` 需要将 `Datastore Indexes` 创建好之后才能使用，可以在 `GAE` 的控制台查看 `Datastore Indexes` 状态

<h2 id="addapp">添加客户端应用到鸟巢采集</h2>

在鸟巢采集 `WEB` 端注册账号，添加采集器 `http://#your app id#.appspot.com/` 即可开始采集任务。