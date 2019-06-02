进阶操作
============

机器翻译
---------------

BasicCAT预置了以下12种机器翻译引擎的API的支持：

* `百度 <http://api.fanyi.baidu.com/api/trans/product/prodinfo>`_
* `谷歌 <https://cloud.google.com/translate/>`_
* `微软必应 <https://azure.microsoft.com/services/cognitive-services/translator-text-api/>`_
* `小牛 <https://niutrans.vip/index/niutrans/index.html>`_
* `有道 <http://ai.youdao.com/>`_
* `Yandex <https://tech.yandex.com/translate/>`_
* `MyMemory <https://mymemory.translated.net/doc/spec.php>`_
* `搜狗（旧版免费接口） <http://ai.sogou.com/ai-docs/api/fanyi>`_
* `搜狗深智 <https://deepi.sogou.com/>`_
* `腾讯云翻译 <https://cloud.tencent.com/product/tmt>`_
* `IBM Watson <https://www.ibm.com/watson/services/language-translator/>`_
* `亚马逊 <https://aws.amazon.com/translate/>`_


调用结果如下图。

.. image:: /images/machine_translation.png

您需要申请翻译API以实现调用，每个机器翻译申请的链接已经附在上面的列表中，其中MyMemory只需要配置一个email地址即可使用。划词检索和自动完成功能需要至少配置一个机器翻译才能使用。

点击菜单Options->Preferences进入设置界面，选择Machine Translation进行翻译API的配置。

.. image:: /images/machine_translation_setting.png

.. image:: /images/machine_translation_filler.png

机器翻译的API服务都有使用限制，百度和微软每个月200万词免费额度；MyMemory每天10000词；Yandex每天1百万词，每月不超1千万词。其它需要付费使用，小牛和有道注册时会附赠百万词的额度。


预翻译
---------------

预翻译指利用翻译记忆或者机器翻译预先对全文进行翻译。点击菜单Project->Pre-translate打开对话框，选择使用翻译记忆或者机器翻译进行预翻译。可以设置翻译记忆的最低匹配率和选择使用哪个机器翻译引擎。

.. image:: /images/pretranslate.png

.. image:: /images/pretranslating.png


划词取义
---------------

利用机器翻译和在线词典API，BasicCAT提供划词检索功能。在原文中选中需要检索的部分，可以显示机器翻译或者在线词典的内容。需要在设置中勾选这一功能，并配置至少一个机器翻译。

.. image:: /images/lookup.png

点击出现的下拉框中的项目可以把结果添加到译文输入框。

在线词典
---------------

因为离线词典往往具有版权问题，所以BasicCAT选择了集成在线词典。

在原文中选中一个单词后，点击菜单Edit->Show online dictionary dropdown，或者使用快捷键Ctrl+D，会出现包含一串在线词典名字的下拉列表。点击后会打开一个浏览窗口。

.. image:: /images/online_dictionary.png

.. image:: /images/online_dictionary_dropdown.png

.. image:: /images/online_dictionary_form.png

选中想输入的释义后，按Add Selected可以填充进译文输入框。按Open in browser可以使用本地浏览器访问该页面。

你可以通过修改项目文件夹下的config文件夹里的dictList.txt添加其它在线词典。

语言检查
---------------

BasicCAT利用 `Language Tool <https://www.languagetool.org/>`_ 作为语言检查的后端。Language Tool是一款开源的拼写和语法检查器。

在一个片段翻译完成，按下回车切换到下一片段后，会对上一片段进行检查。如果有错误，会在下方的功能区进行提示，并在输入框位置显示一个备选正确内容的下拉列表。点击功能区的replacement项目或者下拉列表的项目可以替换译文中的错误为正确的内容。

.. image:: /images/languagecheck.png

要使用语言检查，你可以选择直接使用LanguageTool的API（默认地址：https://languagetool.org/api/v2/check），或者下载LanguageTool后在本地运行。

`LanguageTool 4.3 下载 <https://www.languagetool.org/download/LanguageTool-4.3.zip>`_

下载后解压至任意位置，然后打开BasicCAT，点击菜单Tools->Server Launcher，打开服务启动器的窗口，选择存放languagetool-server.jar这一文件的文件夹。然后点击Start LanguageTool Server的按钮后可以在本地运行LanguageTool的离线服务。

.. image:: /images/serverlauncher.png

可以用浏览器访问 `<http://127.0.0.1:8081/v2/check?text=a%20example&language=en-US>`_ 来判断服务是否运行。

除此之外，你还要设置启用语言检查。点击菜单Options->Preferences，进入Language Check页面，勾选启用语言检查。

.. image:: /images/lauguagecheck_setting.png

你还可以设置每次以下拉列表形式给出建议的最大数量，以免有的时候显示的建议太多。


自动完成（交互式机器翻译）
-----------------------------

自动完成对原文进行分词，并利用斯坦福自然语言处理工具进行句法分析，提取短语，所得的片段利用机器翻译进行翻译，如果在翻译过程中输入的字是某个片段的开头，那这一片段的译文会以下拉列表的形式供用户选择是否使用。

.. image:: /images/autocomplete.png

对于汉译英，还可以用于快速输入英文单词。

.. image:: /images/autocomplete_c2e.png

要使用自动完成，需要下载斯坦福自然语言处理软件。

官网地址：https://stanfordnlp.github.io/CoreNLP/index.html

百度网盘（备用）：https://pan.baidu.com/s/1LNW4IDw8Viz6RURmzqxI9Q

需要下载corenlp和中文的模型文件。下载完成后解压corenlp-full的zip文件到任意位置，把中文模型文件放入解压的目录，然后点菜单Tools->Server Launcher，选择文件夹位置后点Start CoreNLP Server按钮启动。

可以用浏览器访问 `<http://127.0.0.1:9000>`_ 来判断服务是否运行。

和Language Tool一样，还需要设置启用自动完成。点击菜单Options->Preferences，进入Autocomplete页面，勾选启用自动完成。

如果想使用运行在远程服务器的corenlp，可以通过修改链接来调用。

你还可以设置每次以下拉列表形式给出建议的最大数量，以免有的时候显示的建议太多。

快速填充
---------------

翻译过程中我们常常需要输入特殊的符号，或者需要多次输入同一串文本。BasicCAT支持定义快速填充项目，在翻译时使用快捷键Ctrl+Q或者点击菜单Edit->Show quickfill dropdown来显示快捷输入用的下拉列表。如果匹配到术语，也可以设置包含进去。

.. image:: /images/quickfill.png

快速填充的设置需要点击菜单Project->Project Settings，切换到Quickfill栏目。

.. image:: /images/quickfill_setting.png

自动更正
---------------

自动更正是借鉴自Word的一项功能，可以检测输入的内容，对内容进行修正。比如英译汉时需要输入中文的标点符号，可以设置错误地输入英文标点符号时自动更正为中文标点。我们也可以用它来快速输入内容。比如rst是restructuredText的缩写，设置自动更正后，每次输入rst，内容就会自动变成restructuredText。

.. image:: /images/autocorrect.gif

点击菜单Project->Project Settings，切换到AutoCorrect栏目进行设置。

.. image:: /images/autocorrect.png

导出Word以供审校
-----------------------

BasicCAT支持导出翻译的内容至Word中，利用Word的审校功能进行审校。

在所需导出的文件上右键，点击Export to->docx for review，可以导出docx文件。

.. image:: /images/export.png

.. image:: /images/word_review.png

完成审校后，可以从Word文件将修改结果导回。在文件名上右键，点击Import form review。

.. image:: /images/import_review.png

你可以一条一条地重新确认，也可以直接用审校的内容替换原来的翻译。

.. image:: /images/review_confirm.png

导出双语对照文本
-------------------

在所需导出的文件上右键，点击Export to->bi-paragraphs，可以导出双语段落对照文本。

.. image:: /images/export.png

导出带备注的Markdown文件
---------------------------------

和上一条操作办法相近，在所需导出的文件上右键，点击Export to->Markdown with notes，可以导出Markdown文件。

Markdown文件可以使用\ `Pandoc <http://www.pandoc.org/>`_\ 进一步转换成Word文件。


搜索与替换
---------------

点击菜单Edit->Search and Replace进入搜索与替换对话框，可以检索原文和译文的内容。支持使用正则表达式。

下面是利用正则表达式将英文引号替换成中文引号的例子。

.. image:: /images/search_and_replace.png

关于正则表达式，可以参考\ `这里 <http://www.runoob.com/regexp/regexp-tutorial.html>`_\ 的教程。