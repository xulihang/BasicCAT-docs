快速入门
==================================================

新建项目
-----------

菜单栏点击File->New，选择建立英译汉(en to zh)、汉译英(zh to en)项目或者其它语言对的项目，会自动生成翻译记忆库和术语库等项目文件。

.. image:: /images/new_project.png

选择其它语言对时你也可以自己输入所需的遵循ISO639标准的语言代码，具体说明\ `见此 <http://www.basiccat.org/1-2-beta-has-multilanguage-support/>`_\ 。

.. image:: /images/select_languagepair.png

新建项目后要进一步操作需要先保存项目。

添加文件
+++++++++

打开项目后在左侧会显示一列项目，可以操作项目文件、翻译记忆、术语库，查看统计信息和预览。

.. image:: /images/project_area.png

我们在Project Files上右键，可以添加文件或者添加文件夹。

.. image:: /images/add_file.png

添加文件后点击文件名，可以打开该文件进行翻译，并进入下图的界面。每个功能分区都已在图中标出。在原文右边的编辑框中输入文字即可开始翻译，一个片段完成后按回车切换到下一片段。

.. image:: /images/main_with_texts.png

翻译记忆
-----------

片段翻译完成后按回车，该条翻译的内容就会自动加入翻译记忆库。在遇到相似的片段时，便会在下方显示。点击该条结果即可将译文填充进译文输入框。

.. image:: /images/fuzzy_match.png

翻译记忆的匹配率可以点击菜单栏Project->Project Settings进行设置。匹配率须在0.5到1.0之间。

.. image:: /images/fuzzy_match_setting.png

添加外部翻译记忆
++++++++++++++++

BasicCAT的翻译记忆库分为项目记忆库和外部记忆库。项目记忆库存储项目文件的翻译记忆，而外部记忆库显示外部导入的翻译记忆。

点击菜单栏Project->Project Settings，选中TM一栏设置可以进行外部翻译记忆的管理。

支持导入TMX格式和Tab分割的txt文件，txt文件要求原文在前，译文在后，以tab进行分割。添加文件时会显示一个预览窗口，便于检验导入的内容是否正确。

.. image:: /images/project_setting_tm.png

.. image:: /images/importpreview.png

模糊匹配到外部记忆库的片段时，会在下方显示，并显示来自哪个记忆库文件。翻译记忆中的原文、当前要翻译的原文和翻译记忆中的译文会在差异显示区显示。

.. image:: /images/match_result.png

管理翻译记忆
++++++++++++

点击项目区的Translation Memory可以对翻译记忆进行检索，并进行导出、修改和删除等操作。

.. image:: /images/tm_manager.png

术语管理
------------

在翻译过程中遇到术语，可以在原文和译文中选中对应的文本，然后点击术语区的Add Term添加术语。BasicCAT利用opennlp自然语言处理工具对词型进行还原，避免保存的是词语的复数形式而匹配不到词语的单数形式等问题。

.. image:: /images/term_match.png

在显示的术语条目上右键，可以查看更多信息和修改历史。

.. image:: /images/term_more.png

.. Attention::
    考虑到导入的外部术语库可能有上万条内容，为了优化匹配的速度，采用的HashMap的算法，只能对要翻译的原文进行词型还原。所以平时添加术语最好还是添加原形，方便导入其它项目。

术语的导入和翻译记忆的导入类似，支持的文件类型是TBX和Tab分割的TXT文件。

术语的管理界面也和翻译记忆的类似，不同之处在于术语可以添加标签和备注进行管理。

.. image:: /images/term_manager.png

片段操作
-------------

BasicCAT利用SRX分割标准对原文进行分割。片段多为一个句子或者一个单独成段的短语。

片段合并与分割
+++++++++++++++++

遇到下图这样的人名分割错误的情况，我们可以点击原文的末尾，然后按Delete键进行句段合并操作。

.. image:: /images/merge_segments.png

如果句段属于不同的文件或者翻译单元，将不能进行合并。word中的不同段落，indesign中不同的story文件都属于这种情况。

.. image:: /images/merge_segments_different_transunits.png

BasicCAT对不需要显示的格式标签进行了隐藏处理，如果合并的片段带标签，也会进行提示。此时可以选择继续进行合并，但可能会显示出较为复杂的标签。

.. image:: /images/merge_segments_hidden_tags.png

遇到下图这样需要在分号处进行分割的片段，将光标定位到分号后，按Enter键进行分割。

.. image:: /images/split_segments.png

忽略片段
+++++++++++++++

英译汉时常碰到前一片段和后一片段意思有重复，只需翻译后一片段的情况。这时可以忽略前一片段。这样，生成译文时会自动忽略这一片段。可以通过点击菜单Edit->Mark the current segment as neglected进行设置。

设置忽略的片段的编辑区会变成灰色不可用状态。

.. image:: /images/mark_neglected_example.png

添加备注
+++++++++++++

翻译中碰到较难的句子，可以进行备注，记录为什么这样翻。点击菜单栏Edit->Show/Edit notes of the current segment进行查看或修改操作。

.. image:: /images/note_edit.png

含有备注的片段的译文编辑框会显示一圈绿色。

.. image:: /images/segment_with_note.png

查看片段历史
+++++++++++++++++

BasicCAT会记录片段的修改历史，点击菜单Edit->Show segment history即可查看历史，其中的用户名即版本控制设置中添加的用户名。

.. image:: /images/history_viewer.png


查看项目统计信息
--------------------

点击项目区的Statistics，可以显示项目的统计信息，比如原文字数、译文字数和完成的百分比等。

.. image:: /images/statistics.png

查看预览
--------------------

点击项目区的Preview，可以对翻译的内容进行预览。已经翻译的部分会用译文进行替代。

.. image:: /images/preview.png

生成目标文件
-------------------

翻译结束后，点击菜单File->Generate target files，即可在项目的target文件夹里生成目标文件。

.. image:: /images/generate.png