OpenShift上安装鸟巢采集客户端应用
=========================

*   [需要安装的环境](#env)
*   [注册OpenShift账号](#signup)
*   [建立OpenShift JAVA应用](#create)
*   [发布鸟巢采集器到OpenShift](#deploy)
*   [安装鸟巢采集器](#install)
*   [添加客户端应用到鸟巢采集](#addapp)

* * *

<h2 id="env">需要安装的环境</h2>

<span id="git">Git</span>

<https://msysgit.github.io/>

<span id="tortoisegit">TortoiseGit</span>

<https://code.google.com/p/tortoisegit/wiki/Download?tm=2>

<span id="puttygen">Puttygen</span>

<http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html>

<h2 id="signup">注册OpenShift账号</h2>

<https://www.openshift.com/>

<h2 id="create">建立OpenShift JAVA应用</h2>

1. Create your first application now.

2. Choose a type of application.

		Java>Tomcat 7 (JBoss EWS 2.0)

3. Configure the application

4. Next steps. 

		select “Yes, help me get started”

5. 使用 `Puttygen.exe` 生成秘钥，如下图：

  ![keygen.png](/static/img/openshift/keygen.png)
  
  <br />

6. 复制 `Public key` 到 `OpenShift` 并保存

		复制 `Public key` 到 `Paste the contents of your public key file (.pub)` 下方的文本域中，再点击保存。

  ![paste-save.png](/static/img/openshift/paste-save.png)
  
  <br />

7. 保存私钥 `Save private key`

		如： `C:\App\linux\openshift\qiw-spider.ppk` ，发布文件到 `OpenShift` 时需要私钥。

<h2 id="deploy">发布鸟巢采集器到OpenShift</h2>

1. 新建 `Git` 文件夹

		如： `D:\git_openshift\qiw_spider` ，打开此文件夹，鼠标右击选择  `Git Clone…`，如图：

  ![git-clone.jpg](/static/img/openshift/git-clone.jpg)
  
  <br />

2. Git Clone

  ![git-clone-code.png](/static/img/openshift/git-clone-code.png)
  
  <br />

3. 上传代码到OpenShift

		删除 `D:\git_openshift\qiw_spider\spider\src\main\webapp` 下的所有文件
		复制鸟巢采集器代码到 `D:\git_openshift\qiw_spider\spider\src\main\webapp` 
		右击空白区域，执行 `Git Sync…`
  ![sync.jpg](/static/img/openshift/sync.jpg)

  ![deploy.jpg](/static/img/openshift/deploy.jpg)

  `Git Sync`

  ![deploy-commit.jpg](/static/img/openshift/deploy-commit.jpg)

  `Commit`

  ![deploy-push.jpg](/static/img/openshift/deploy-push.jpg)

  `Push`

<h2 id="install">安装鸟巢采集器</h2>

1. `OpenShift` 的 `Applications` 页安装 `MySQL`、`phpMyAdmin`，如:

  ![applications.png](/static/img/openshift/applications.png)
  
  <br />

2. 访问“<http://spider-qiw.rhcloud.com/>”开始安装鸟巢采集器

  ![install.png](/static/img/openshift/install.png)
  
  <br />

3. 显示“恭喜您，系统已经安装成功！”表示安装完成。

		访问“<http://spider-qiw.rhcloud.com/>”提示 `It works!` 表示安装成功。

<h2 id="addapp">添加客户端应用到鸟巢采集</h2>

在鸟巢采集WEB端注册账号，添加采集器“http://spider-qiw.rhcloud.com/”即可开始采集任务。