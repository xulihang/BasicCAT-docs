团队协作
============

共享翻译记忆、术语
-------------------------

利用BasicCAT的服务器端程序，可以架设用于共享翻译记忆和术语的服务。该程序可以在BasicCAT的下载页面获取。

客户端需要进行相关设置，设置完成后即可实时共享翻译记忆与术语。

.. image:: /images/setting_sharedTMandTerm.png

服务器程序运行的方法（需要安装java8以上版本）：

::

    $ nohup java -jar CloudKVS_Server.jar &

你可以修改程序所在目录下key.txt来添加一个访问密钥。密钥目前只支持单行内容。

基于Git进行团队协作
-------------------------

BasicCAT可以在本地生成git仓库，添加remote uri和账号密码后即可把本地的记录上传到远程，并与其它用户进行协作。每次请求git push时，程序会自动从远程仓库获取最新的变动，并更新本地文件，然后将本地的修改进行上传。BasicCAT会根据片段修改的时间自动解决冲突，基本不会发生冲突的情况。

需要在项目设置里设置远程仓库地址并选择是否每次执行保存操作时把修改上传到远程仓库。你需要在偏好设置里先设置好git账户。

.. image:: /images/setting_git.png

你也可以通过菜单手动进行git的相关操作。

.. image:: /images/git_menu.png

基于Git的协作并不同步翻译记忆与术语，只同步工作文件。

GitHub操作示例
+++++++++++++++++

GitHub是一个流行的Git托管平台，我们可以基于它进行协作。

首先建立一个空的仓库：

.. image:: /images/github/new.png

.. image:: /images/github/create_repo.png

进入以下设置界面：

.. image:: /images/github/setup.png

之后用BasicCAT打开一个项目，在项目设置-团队协作里设置远程仓库。

.. image:: /images/github/set_remote.png

之后将这个项目分发给其它用户即可。

其它用户要想修改远程仓库，还需要获得push的权限。

进入GitHub的仓库设置，点击左边的Collaborators然后添加要添加的GitHub账户。

.. image:: /images/github/repo_setting.png

更多内容可以见GitHub的\ `帮助文档 <https://help.github.com/>`_\ 。

