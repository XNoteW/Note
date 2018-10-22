翻译自 《Python学习手册(第5版)》

## Systems Programming

Python 对操作系统服务的内置接口使其非常适合编写可移植、可维护的系统管理工具和实用程序 utilities (有时称为 shell 工具)。Python 程序可以搜索文件和目录树、启动其他程序、使用进程和线程进行并行处理等等。

Python 的标准库带有 POSIX 绑定和对所有常用 OS 工具的支持: 环境变量、文件、套接字、管道、进程、多线程、正则表达式模式匹配、命令行参数、标准流接口、shell 命令发射器、文件名扩展、zip 文件实用程序、XML 和 JSON 分析器、CSV 文件处理程序等。此外, Python 的大部分系统接口设计为可移植; 例如, 复制目录树的脚本通常在所有主要 Python 平台上运行不变。EVE Online 采用 Stackless Python 的实现并提供了针对多处理需求的高级解决方案。

## GUIs (用户图形接口)

Python 的简洁和快速周转也使它成为桌面上图形用户界面编程的好匹配。python 附带了一个标准面向对象的接口, 该 API 称为 tkinter (tkinter 2.X), 它允许 Python 程序实现具有本地外观和感觉的便携式 gui。Python/tkinter gui 在 Windows、X  Windows ( Unix 和 Linux ) 和 Mac os (经典版和 OS x) 上运行不变。一个免费的扩展包, PMW, 添加高级小部件到 tkinter 工具包。此外, 基于 c++ 库的 wxPython GUI API 提供了一种在 Python 中构建便携式 gui 的替代工具包。

更高级别的工具包 (如达博) 建立在基本 api (如 wxPython 和 tkinter) 之上。使用适当的库, 您还可以在 Python 中的其他工具包中使用 GUI 支持, 例如 Qt 与 PyQt、具有 PyGTK 的 GTK、带有 PyWin32 的 MFC、. NET 和 IronPython, 以及使用 Jython (2 章中描述的 Java 版本的 Python) 或 JPype 进行摆动。对于在 web 浏览器中运行或具有简单接口要求的应用程序, Jython 和 Python web 框架和服务器端 CGI 脚本提供其他用户界面选项。

## Internet Scripting

python 附带了标准的 Internet 模块, 允许 python 程序在客户端和服务器模式下执行各种网络任务。脚本可以通过套接字进行通信;提取发送到服务器端 CGI 脚本的表单信息;通过 FTP 传输文件;分析和生成 XML 和 JSON 文档;发送、接收、撰写和分析邮件; 按 URL 获取网页;解析获取的网页的 HTML;通过 XML (RPC、SOAP 和 Telnet) 进行通信等等。Python 的库使这些任务非常简单。

不仅如此, Web 上还提供了大量的第三方工具, 用于 Python 中的 Internet 编程。例如, HTMLGen 系统生成基于 Python 类的描述的 HTML 文件, *mod_python* 包在 Apache web 服务器中高效运行 Python, 并支持服务器端模板化及其 Python 服务器页面, 以及 Jython 系统提供无缝 Python/Java 集成, 并支持在客户端上运行的服务器端小程序的编码。

此外, 对于 python, 如 Django、TurboGears、web2py、Pylons、Zope 和 WebWare, 完整的 web 开发框架包支持使用 python 快速构建全功能和生产质量的网站。其中许多功能包括对象关系映射器、模型/视图/控制器体系结构、服务器端脚本和模板以及 AJAX 支持, 以提供完整的企业级 web 开发解决方案。

最近, Python 已扩展到丰富的 Internet 应用程序 (RIAs), 其中包括 IronPython 中的 Silverlight 和 pyjs (也称为睡衣 ( pyjamas)) 及其 Python 到 JavaScript 编译器、AJAX 框架和小部件集。Python 还已迁移到云计算、应用引擎以及前面的数据库部分中描述的其他内容。在 Web 潜在客户的位置, Python 很快就会跟随。

## Component Integration (组件集成)

Python 在 c 和 c++ 系统中扩展和嵌入的能力使其成为一种灵活的胶水语言, 用于编写其他系统和组件的行为脚本。例如, 将 C 库集成到 python 使 python 能够测试和启动库的组件, 并在产品中嵌入 Python, 无需重新编译整个产品 (或根本不发运其源代码) 即可对现场自定义进行编码。

诸如 SWIG 和 SIP 代码生成器之类的工具可以自动完成将编译的组件链接到 python 以便在脚本中使用所需的大部分工作, 而 Cython 系统允许程序员混合 python 和类似 C 的代码。更大的框架, 如 Python 在 Windows 上的 COM 支持、基于 Jython Java 的实现和 IronPython。基于 .NET 的实现提供了脚本组件的其他方法。例如, 在 Windows 上, Python 脚本可以使用框架来编写 Word 和 Excel 的脚本、访问 Silverlight 等。

## Database Programming

对于传统的数据库需求, 对于所有常用的关系数据库系统 (Sybase、Oracle、Informix、ODBC、MySQL、PostgreSQL、SQLite 等) 都有 Python 接口。python 世界还定义了一个可移植数据库 API, 用于从 Python 脚本访问 SQL 数据库系统, 在各种基础数据库系统上看起来相同。例如, 由于供应商接口实现了便携式 API, 编写用于与免费 MySQL 系统一起工作的脚本在其他系统 (如 Oracle) 上的工作基本不变;您通常需要做的就是更换基础供应商界面。自2.5 以来, 进程内 SQLite 嵌入式 SQL 数据库引擎是 Python 本身的标准部分, 支持原型设计和基本程序存储需求。

在非 SQL 部分中, Python 的标准 `pickle` 模块提供了一个简单的对象持久化系统-它允许程序轻松地将整个 Python 对象保存和还原到文件和类似文件的对象。在 Web 上, 您还可以找到名为 ZODB 和 Durus 的第三方开源系统, 为 Python 脚本提供完整的面向对象的数据库系统;其他, 如 SQLObject 和 SQLAlchemy, 实现对象关系映射器 (ORMs), 将 Python 的类模型移植到关系表上;PyMongo 是 MongoDB 的一个接口, 它是一种高性能、非 SQL、开放源码的 JSON 样式文档数据库, 它将数据存储在结构非常类似于 python 自己的列表和字典中, 其文本可以使用 python 自己的标准库 json 模块进行分析和创建。

此外, 其他系统还提供了更专业的方法来存储数据, 包括在 Google App 引擎中使用数据存储, 通过 Python 类来建模和提供广泛的可扩展性, 以及其他新兴云存储选项, 如 Azure、PiCloud、OpenStack 和 Stackato。

## Rapid Prototyping (快速原型)

对于 python 程序, 用 python 和 C 编写的组件看起来是一样的。因此, 最初可以在 Python 中原型系统, 然后将所选组件移动到编译语言 (如 c 或 c++) 以进行传递。与某些原型工具不同, Python 在原型凝固后不需要完全重写。不需要 C + + 等语言效率的系统部分可以保持在 Python 中编码, 便于维护和使用。

## Numeric and Scientific Programming

python 在数字编程中也被大量使用, 这是一种传统上不被认为是脚本语言范围的领域, 但已经发展成为 python 最引人注目的用例之一。这里突出的是, 前面提到的 Python 的 NumPy 高性能数字编程扩展包括诸如数组对象的高级工具、标准数学库的接口等等。通过将 python 与以编译语言编码的数字例程集成为速度, NumPy 将 python 转换为复杂而易于使用的数字编程工具, 通常可以替换传统编译语言 (如 FORTRAN 或 C++) 编写的现有代码。

Python 支持动画、3D 可视化、并行处理等其他数字工具。例如, 流行的 SciPy 和 ScientificPython 扩展提供了更多的科学编程工具库, 并将 NumPy 作为核心组件使用。Python 的 PyPy 实现也在数字领域中得到了牵引, 部分原因是此域中常见的排序的大量算法代码可以在 PyPy 中快速运行, 通常速度快10X 到 100X。

## Gaming, Images, Data Mining, Robots, Excel 等

Python 通常应用在更多的域中, 而不是可以在这里覆盖。例如, 您将找到允许您使用 Python 执行以下操作的工具:

- 游戏编程和多媒体：pygame, cgkit, pyglet, PySoy, Panda3D, ...
- 通过 PySerial 扩展, 在 Windows、Linux 和更多端口上进行串口通信
- 使用 PyRo 工具包进行机器人控制编程
- 使用 NLTK 包进行自然语言分析
- 树莓派 (Raspberry Pi) 和 Arduino 板上的仪器仪表工具
- 移动 (Mobile) 计算: Python 端口到谷歌 Android 和苹果 iOS 平台
- Excel 电子表格功能和宏编程: PyXLL 或 DataNitro 加载项
- 媒体文件内容和元数据标签处理 (Media file content and metadata tag processing): PyMedia, ID3, PIL/Pillow 等
- 人工智能: PyBrain 神经网络库和 Milk 机器学习工具包
- 专家系统: PyCLIPS, Pyke, Pyrolog, pyDatalog
- 网络监视 (Network monitoring): zenoss, 使用 Python 进行编写和自定义
- Python 脚本设计和建模: PythonCAD、PythonOCC、FreeCAD 和其他
- 文件处理和生成 (Document processing and generation): ReportLab, Sphinx, Cheetah, PyPDF 等等
- 使用 Mayavi、matplotlib、VTK、VPython 等进行数据可视化
- xml 分析: xml 库包、xmlrpclib 模块和第三方扩展
- JSON, CSV 文件处理: `json` and `csv` modules
- 数据挖掘: 使用 Orange 框架、Pattern bundle、Scrapy 和自定义代码

## 其他

### Scikit-learn（重点推荐）

[Scikit-learn](www.github.com/scikit-learn/scikit-learn) 是基于 Scipy 为机器学习建造的的一个 Python 模块，他的特色就是多样化的分类，回归和聚类的算法包括支持向量机，逻辑回归，朴素贝叶斯分类器，随机森林，Gradient Boosting，聚类算法和 DBSCAN。而且也设计出了 Python numerical 和 scientific libraries Numpy and Scipy

### Keras（深度学习）

[Keras](https://github.com/fchollet/keras) 是基于 Theano, Tensorflow, CNTK 的一个深度学习框架，它的设计参考了 Torch，用 Python 语言编写，是一个高度模块化的神经网络库，支持 GPU 和 CPU。

### Lasagne（深度学习）

不只是一个美味的意大利菜，也是一个和 Keras 有着相似功能的深度学习库，但其在设计上与它们有些不同。

### Pylearn2

[Pylearn](www.github.com/lisa-lab/pylearn2) 是一个让机器学习研究简单化的基于 Theano 的库程序。它把深度学习和人工智能研究许多常用的模型以及训练算法封装成一个单一的实验包，如随机梯度下降。

### NuPIC

[NuPIC](www.github.com/numenta/nupic) 是一个以 HTM 学习算法为工具的机器智能平台。HTM 是皮层的精确计算方法。HTM 的核心是基于时间的持续学习算法和储存和撤销的时空模式。NuPIC 适合于各种各样的问题,尤其是检测异常和预测的流数据来源。

### Nilearn

[Nilearn](www.github.com/nilearn/nilearn) 是一个能够快速统计学习神经影像数据的 Python 模块。它利用 Python 语言中的 scikit-learn 工具箱和一些进行预测建模，分类，解码，连通性分析的应用程序来进行多元的统计。

### PyBrain

[Pybrain](www.github.com/pybrain/pybrain) 是基于 Python 语言强化学习，人工智能，神经网络库的简称。 它的目标是提供灵活、容易使用并且强大的机器学习算法和进行各种各样的预定义的环境中测试来比较你的算法。

### Pattern

[Pattern](www.github.com/clips/pattern) 是 Python 语言下的一个网络挖掘模块。它为数据挖掘，自然语言处理，网络分析和机器学习提供工具。它支持向量空间模型、聚类、支持向量机和感知机并且用KNN分类法进行分类。

### Fuel

[Fuel](www.github.com/mila-udem/fuel) 为你的机器学习模型提供数据。他有一个共享如MNIST, CIFAR-10 (图片数据集), Google's One Billion Words (文字)这类数据集的接口。你使用他来通过很多种的方式来替代自己的数据。

### Bob

[Bob](www.github.com/idiap/bob) 是一个免费的信号处理和机器学习的工具。它的工具箱是用 Python 和 C++ 语言共同编写的，它的设计目的是变得更加高效并且减少开发时间，它是由处理图像工具,音频和视频处理、机器学习和模式识别的大量软件包构成的。

### Skdata

[Skdata](www.github.com/jaberg/skdata) 是机器学习和统计的数据集的库程序。这个模块对于玩具问题，流行的计算机视觉和自然语言的数据集提供标准的Python语言的使用。

### MILK

[MILK](www.github.com/luispedro/milk) 是Python语言下的机器学习工具包。它主要是在很多可得到的分类比如SVMS,K-NN,随机森林，决策树中使用监督分类法。 它还执行特征选择。 这些分类器在许多方面相结合,可以形成不同的例如无监督学习、密切关系金传播和由MILK支持的K-means聚类等分类系统。

### IEPY

[IEPY](www.github.com/machinalis/iepy) 是一个专注于关系抽取的开源性信息抽取工具。它主要针对的是需要对大型数据集进行信息提取的用户和想要尝试新的算法的科学家。

### Quepy

[Quepy](www.github.com/machinalis/quepy) 是通过改变自然语言问题从而在数据库查询语言中进行查询的一个 Python 框架。他可以简单的被定义为在自然语言和数据库查询中不同类型的问题。所以，你不用编码就可以建立你自己的一个用自然语言进入你的数据库的系统。
现在 Quepy 提供对于 Sparql 和 MQL 查询语言的支持。并且计划将它延伸到其他的数据库查询语言。

### Hebel

[Hebel](www.github.com/hannes-brt/hebel) 是在 Python 语言中对于神经网络的深度学习的一个库程序，它使用的是通过 PyCUDA 来进行 GPU 和 CUDA 的加速。它是最重要的神经网络模型的类型的工具而且能提供一些不同的活动函数的激活功能，例如动力，涅斯捷罗夫动力，信号丢失和停止法。

### mlxtend

[mlxtend](www.github.com/rasbt/mlxtend) 它是一个由有用的工具和日常数据科学任务的扩展组成的一个库程序。

### nolearn

[nolearn](www.github.com/dnouri/nolearn) 容纳了大量能对你完成机器学习任务有帮助的实用程序模块。其中大量的模块和 scikit-learn 一起工作，其它的通常更有用。

### Ramp

[Ramp](www.github.com/kvh/ramp) 是一个在 Python 语言下制定机器学习中加快原型设计的解决方案的库程序。他是一个轻型的 pandas-based 机器学习中可插入的框架，它现存的Python语言下的机器学习和统计工具（比如scikit-learn,rpy2 等）Ramp 提供了一个简单的声明性语法探索功能从而能够快速有效地实施算法和转换。

### Feature Forge

[Feature Forge](www.github.com/machinalis/featureforge)一系列工具通过与 scikit-learn 兼容的 API，来创建和测试机器学习功能。

这个库程序提供了一组工具，它会让你在许多机器学习程序使用中很受用。当你使用 scikit-learn 这个工具时，你会感觉到受到了很大的帮助。（虽然这只能在你有不同的算法时起作用。）

### REP

[REP](www.github.com/yandex/rep) 是以一种和谐、可再生的方式为指挥数据移动驱动所提供的一种环境。

它有一个统一的分类器包装来提供各种各样的操作，例如 TMVA, Sklearn, XGBoost, uBoost等等。并且它可以在一个群体以平行的方式训练分类器。同时它也提供了一个交互式的情节。

### Python 学习机器样品

[machine-learning-sample](www.github.com/awslabs/machine-learning-samples) 用亚马逊的机器学习建造的简单软件收集。

### Python-ELM

[Python-ELM](www.github.com/dclambert/Python-ELM) 这是一个在 Python 语言下基于 scikit-learn 的极端学习机器的实现。

### gensim

主题模型 python实现

- Scalable statistical semantics
- Analyze plain-text documents for semantic structure
- Retrieve semantically similar document