其它
====================

外观设置
-----------------------------

点击菜单Options->Preferences进入设置窗口，点击左边的Appearence，可以进行外观方面的设置。

目前仅支持设置编辑区的字体。

.. image:: /images/fontpicker.png

自动备份
-----------------------------

BasicCAT支持自动备份，可以在设置界面设置间隔多少时间备份一次项目文件。备份的文件会保存在项目的bak文件夹里。

.. image:: /images/general.png

使用Git进行版本控制
-----------------------------

BasicCAT自带的Git，支持每次执行保存时在项目文件夹执行一次git commit操作。

可以在设置里设置执行git commit的用户信息。

.. image:: /images/git_setting.png

安装Git后，在项目文件夹执行git show可以查看最新一次保存做了哪些修改。你也可以用git reset命令回退到之前的历史版本。

.. image:: /images/git.png

更多功能可以通过安装Git桌面客户端来实现。

管理插件
-----------------------------

BasicCAT目前支持开发机器翻译插件和文件过滤器插件。进入设置界面可以选择插件存放的文件夹，执行插件的增删操作。

.. image:: /images/plugins.png
