快速入门
==================================================

新建项目
-----------

菜单栏点击File->New，选择建立英译汉(en to zh)或者汉译英(zh to en)项目，会自动生成翻译记忆库和术语库等项目文件。

.. image:: /images/new_project.png

新建项目后要进一步操作需要先保存项目。

添加文件
+++++++++

打开项目后在左侧会显示一列项目，可以操作项目文件、翻译记忆、术语库，查看统计信息和预览。

.. image:: /images/project_area.png

我们在Project Files上右键，可以添加文件。

.. image:: /images/add_file.png

添加文件后点击文件名，可以打开该文件进行翻译，并进入下图的界面。每个功能分区都已在图中标出。在原文右边的编辑框中输入文字即可开始翻译，一个片段完成后按回车切换到下一片段。

.. image:: /images/main_with_texts.png

翻译记忆
-----------

片段翻译完成后按回车，该条翻译的内容就会自动加入翻译记忆库。在遇到相似的片段时，便会在下方显示。点击该条结果即可将译文填充进译文输入框。

.. image:: /images/fuzzy_match.png

翻译记忆的匹配率可以在点击菜单栏Project->Project Settings进行设置。匹配率须在0.5到1.0之间。

.. image:: /images/fuzzy_match_setting.png

添加外部翻译记忆
++++++++++++++++

BasicCAT的翻译记忆库分为项目记忆库和外部记忆库。项目记忆库存储项目文件的翻译记忆，而外部记忆库显示外部导入的翻译记忆。

点击菜单栏Project-Project Settings，选中TM一栏设置可以进行外部翻译记忆的管理。

支持导入TMX格式和Tab分割的txt文件，txt文件要求原文在前，译文在后，以tab进行分割。

.. image:: /images/project_setting_tm.png

模糊匹配到外部记忆库的片段时，会在下方显示，并显示来自哪个记忆库文件。翻译记忆中的原文、当前要翻译的原文和翻译记忆中的译文会在差异显示区显示。

.. image:: /images/match_result.png

管理翻译记忆
++++++++++++

点击项目区的Translation Memory可以对翻译记忆进行检索，并进行导出、修改和删除等操作。

.. image:: /images/tm_manager.png

术语管理
------------

在翻译过程中遇到术语，可以在原文和译文中选中对应的文本，然后点击术语区的Add Term添加术语。BasicCAT利用opennlp自然语言处理工具对词型进行还原，避免保存的是词语的单数形式而匹配不到词语的复数形式等问题。

.. image:: /images/term_match.png

术语的导入和翻译记忆的导入类似，支持的文件类型是TBX和Tab分割的TXT文件。

术语的管理界面也和翻译记忆的类似，不同之处在于术语可以添加标签和备注进行管理。

.. image:: /images/term_manager.png

片段操作
-------------