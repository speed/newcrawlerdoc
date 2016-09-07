鸟巢采集快速开始
=========================

*   [准备](#ready)
*   [添加采集任务](#create_task)
*   [配置数据采集规则](#data_rules)

*   [添加采集网址](#add_urls)
*   [配置计划任务自动采集](#config_cron)
*   [配置数据发布规则](#deploy_rules)
*   [采集规则有效性监控并使用邮件通知](#check_url)
	*   [配置邮件通知模板](#check_url_1)
	*   [配置数据发布规则](#check_url_2)
	*   [配置网址检测规则](#check_url_3)
	*   [配置网址自动检测计划任务](#check_url_4)
*   [使用同步采集API](#api_fetch)
*   [使用数据导出API](#api_export)
*   [查看实时采集日志](#view_logs)
*   [采集规则备份与恢复](#backup_restore)

* * *


<h2 id="ready">准备</h2>

1.注册NewCrawler账号

2.安装鸟巢采集客户端应用

3.添加客户端应用到鸟巢采集WEB服务端

		进入 `系统设置` > `采集器管理` 添加客户端应用

![add_app.jpg](../../static/img/quickstart/add_app.jpg)

<h2 id="create_task">添加采集任务</h2>

		进入刚添加的采集器节点，点击 `添加采集站点`

![create_task.jpg](../static/img/quickstart/create_task.jpg)


<h2 id="data_rules">配置数据采集规则</h2>

1.打开 `XPath可视化配置`

		进入上一步添加的采集站点，点击 `数据采集规则` ，再点击 `XPath可视化配置`
		
![create_rules.jpg](../static/img/quickstart/create_rules.jpg)

2.设置抓取规则

		选中要抓取的字段

![setxpath.jpg](../static/img/quickstart/setxpath.jpg)

		如果有下一页，设置好下一页链接提取规则
		
![setxpath_next.jpg](../static/img/quickstart/setxpath_next.jpg)
		
		最后点击 `Done` 提示 `success` 表示创建规则成功
		
![setxpath_done.jpg](../static/img/quickstart/setxpath_done.jpg)	

3.抓取测试

		重新点击 `数据采集规则` 刷新数据采集规则页面，可以在 `采集规则` 区域看到自动添加的规则
		点击 `采集测试` 可以看到抓取结果

![fetch_test.jpg](../static/img/quickstart/fetch_test.jpg)			


<h2 id="add_urls">添加采集网址</h2>

		进入 `采集网址列表` 页面，点击 `添加网址` ，在 `网址批量添加` 区域中输入网址然后点击 `添加网址`
		
![addurl.jpg](../static/img/quickstart/addurl.jpg)	

<h2 id="config_cron">配置计划任务自动采集</h2>

		进入 `计划任务管理` 页面，选择 `数据自动采集` ，设置 `执行时间` 可以循环或定时执行，如 `重复` `every 1 hours` 表示每1小时执行一次
		
![configcron.jpg](../static/img/quickstart/configcron.jpg)	


<h2 id="deploy_rules">配置数据发布规则</h2>

		进入 `数据发布规则` 页面，配置发布规则后点击 `添加`
		
![configdeploy.jpg](../static/img/quickstart/configdeploy.jpg)	

<h2 id="check_url">采集规则有效性监控并使用邮件通知</h2>

<h3 id="check_url_1">配置邮件通知模板</h3>

		点击设置，进入 `邮件通知` 页面，配置邮件通知模板如 `采集规则监控` 后点击 `添加`
		
![configemailtemp.jpg](../static/img/quickstart/configemailtemp.jpg)	

<h3 id="check_url_2">配置数据发布规则</h3>

		进入 `数据发布规则` 页面，配置发布规则如 `邮件通知` 后点击 `添加`
		
![configemaildeploy.jpg](../static/img/quickstart/configemaildeploy.jpg)	

<h3 id="check_url_3">配置网址检测规则</h3>

		进入 `网址检测管理` 页面，配置网址检测规则如 `采集规则监控` 后点击 `添加`
		
![configcheck.jpg](../static/img/quickstart/configcheck.jpg)	

<h3 id="check_url_4">配置网址自动检测计划任务</h3>

		进入 `计划任务管理` 页面，选择 `网址自动检测` ，设置 `执行时间` 可以循环或定时执行，如 `重复` `every 5 minutes` 表示每5分钟执行一次
		
![configcroncheck.jpg](../static/img/quickstart/configcroncheck.jpg)	

<h2 id="api_fetch">使用同步采集API</h2>

		进入 `采集网址列表` 页面，点击 `添加网址` ，查看采集API `http://112.124.49.24:8700/api/url/fetch?siteId=19&urls=`
		
![apifetchurl.jpg](../static/img/quickstart/apifetchurl.jpg)	

		使用采集API `http://112.124.49.24:8700/api/url/fetch?siteId=19&urls=http%3a%2f%2flist.jd.com%2flist.html%3fcat%3d9987%2c653%2c655`
		
![apifetchurltest.jpg](../static/img/quickstart/apifetchurltest.jpg)

<h2 id="api_export">使用数据导出API</h2>

		进入 `采集到的数据` 页面，点击 `数据导出` ，查看数据导出API `http://112.124.49.24:8700/api/data/export?siteId=19&pageNum=1&type=json`
		
![apiexportdata.jpg](../static/img/quickstart/apiexportdata.jpg)	

		设置 `属性映射` ，点击 `保存`
		
![apiexportdatamap.jpg](../static/img/quickstart/apiexportdatamap.jpg)

		使用数据导出API `http://localhost:8600/api/data/export?siteId=1&pageNum=1&type=json`
		
![apiexportdatatest.jpg](../static/img/quickstart/apiexportdatatest.jpg)

<h2 id="view_logs">查看实时采集日志</h2>

		点击底部的显示日志图标![logviewer.jpg](../static/img/quickstart/logviewer.jpg)	 ，开启实时日志查看，再次点击底部的显示日志图标![logviewer.jpg](../static/img/quickstart/logviewer.jpg) ，将关闭实时日志查看。
		
![consoleviewlogs.jpg](../static/img/quickstart/consoleviewlogs.jpg)	
	
<h2 id="backup_restore">采集规则备份与恢复</h2>

		进入 `站点备份恢复` 页面，点击 `备份` ，将备份采集任务的所有配置信息，不包括 `采集网址列表` 与 `采集到的数据`
		
![backup.jpg](../static/img/quickstart/backup.jpg)	

		进入 `站点备份恢复` 页面，选择备份的压缩包，点击 `恢复` ，可以恢复所备份采集任务的所有配置信息
		
![restore.jpg](../static/img/quickstart/restore.jpg)	
