Aliyun Cloud Engine上安装鸟巢采集客户端应用
=========================

*   [注册Aliyun账号](#signup)
*   [开通云引擎ACE](#goace)
*   [创建JAVA应用环境](#create)
*   [开通MySQL扩展服务](#create_mysql)
*   [修改采集器客户端MySQL配置](#update_config)
*   [上传采集器客户端](#upload_war)
*   [添加客户端应用到鸟巢采集](#addapp)

* * *


<h2 id="signup">注册Aliyun账号</h2>

<https://account.aliyun.com/register/register.htm>


<h2 id="goace">开通云引擎ACE</h2>

<http://ace.console.aliyun.com/>

<h2 id="create">创建JAVA应用环境</h2>

![create_java.jpg](static/img/ace/create_java.jpg)

![create_java_finish.jpg](static/img/ace/create_java_finish.jpg)

<h2 id="create_mysql">开通MySQL扩展服务</h2>

![create_mysql.jpg](static/img/ace/create_mysql.jpg)

<h2 id="update_config">修改采集器客户端MySQL配置</h2>

1.下载采集器客户端 `soso-crawler.war` 

2.解压  `soso-crawler.war` 

3.重命名数据库配置文件

		`WEB-INF/classes/datanucleus_bak.properties` to `WEB-INF/classes/datanucleus.properties`
	
4.修改数据库配置 `WEB-INF/classes/datanucleus.properties`

		原配置
		javax.jdo.option.ConnectionURL=jdbc:mysql://127.0.0.1:3306/newcrawler?characterEncoding=UTF-8
		javax.jdo.option.ConnectionUserName=root
		javax.jdo.option.ConnectionPassword=

		改为ACE的MySQL配置
		javax.jdo.option.ConnectionURL=jdbc:mysql://#外网地址#:3306/#数据库#?characterEncoding=UTF-8
		javax.jdo.option.ConnectionUserName=#账户名#
		javax.jdo.option.ConnectionPassword=#数据库密码#
		
提示：不知道数据库密码可去数据库控制台重置密码
	
![reset_pas.jpg](static/img/ace/reset_pas.jpg)
	

5.重新打包

		将解压的所有文件打包成zip `soso-crawler.zip` 
		再重命名 `soso-crawler.zip` 到  `soso-crawler.war` 
	
![zip.png](static/img/ace/zip.png)
	
<br />
	
<h2 id="upload_war">上传采集器客户端</h2>

1.进入 `应用列表` ，选中刚刚创建的应用，点击 `管理` ，再进入 `版本管理`
	
![create_version.jpg](static/img/ace/create_version.jpg)

<br />

2.创建版本

![upload_war.jpg](static/img/ace/upload_war.jpg)

<br />

3.上传成功后勾选 `需要立即部署该版本` ，点击确定

![deploy.jpg](static/img/ace/deploy.jpg)

4.查看部署状态，运行状态显示 `运行中` 表示部署完成

![deploy_status.jpg](static/img/ace/deploy_status.jpg)

5.访问“<http://newgo.aliapp.com/>”提示 `It works!` 表示安装成功。


<h2 id="addapp">添加客户端应用到鸟巢采集</h2>

在鸟巢采集WEB端注册账号，添加采集器“http://newgo.aliapp.com/”即可开始采集任务。