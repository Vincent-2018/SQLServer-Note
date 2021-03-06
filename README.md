SQL Server笔记（上海建桥学院）
===

一、数据库系统基本概述
---

### 1.数据库发展过程（三个阶段）

#### 1.1人工数据管理阶段

依靠硬件系统，用于计算输入输出很少数据。

> 特点：
>
> ①数据面向计算相关的应用
>
> ②无数据文件处理软件
>
> ③数据无法存取
>
> ④数据不独立

#### 1.2文件系统管理数据阶段

在操作系统中有专门的数据管理软件，称为文件系统。

> 特点：
>
> ①数据以文件保存
>
> ②数据无法共享
>
> ③数据不独立
>
> ④数据管理功能简单
>
> 缺点：
>
> ①数据不共享冗余大
>
> ②数据不一致
>
> ③数据文件缺乏关联

#### 1.3数据库系统阶段

DBMS（Data Base Management System)软件不断涌现，数据库管理技术不断完善，形成了“数据库时代”。

> 特点：
>
> ①数据共享冗余低
>
> ②数据统一管理和控制
>
> ③数据独立性强
>
> ④结构化集成

### 2.数据库系统的主要特点

相关概念

#### 2.1信息

（Infornation）是客观事物状态、特征在人脑中的反映，是通过人脑抽象后形成的概念及描述，是进行决策的重要依据。

#### 2.2数据

（Data）是信息的表达方式和载体。是人们描述客观事物及其活动的抽象表示，是描述事物的符号记录，是利用信息技术进行采集、处理、存储和传输的基本对象。

> 数据的概念包括两方面含义：
>
> ①是数据的内容-含义（实质）是信息。
>
> ②是数据的表现形式是符号（记录）。

#### 2.3数据处理

数据处理是对数据操作加工的过程。最数据进行的查询、分类、修改、变换、运算、统计、汇总等都是数据处理。其目的是根据需要，从大量的数据中抽取有意义、有价值的数据，其实质是信息处理。

#### 2.4数据库

是机构化的相关数据的集合。可理解为“按一定结构存储管理数据的库”，在机器内、有组织、可共享、长期存储的数据集合。数据库中的数据可按一定的数据模型进行组织、描述和存储。

#### 2.5数据库系统

是具有数据库功能特点的系统。实现有组织地、动态地存储大量关联数据、方便多用户访问的软硬件和数据资源组成的系统。

> 主要特点：
>
> ①数据统一管理控制和规范
>
> ②数据整体结构化
>
> ③数据高共享低冗余易扩充
>
> ④数据独立性高且程序维护便利
>
> ⑤数据完整性和安全性高
>
> ⑥保证数据一致性

#### 2.6数据库管理系统

指建立、运用、管理和维护数据库，并对数据进行统一管理和控制的系统软件。用于建立、操作、管理、控制数据库和数据，保证数据的安全性、完整性、多用户对数据并发操作。DBMS是整个数据库系统的核心。常见的大型关系DBMS有MySQL、SQL Server。

> 数据的独立性包括
>
> ①物理独立性：应用程序与存储数据相互独立；
>
> ②逻辑独立性：应用程序与数据库的逻辑结构相互独立，当数据的逻辑结构（数据元素）改变时，用户程序不受影响。

> 数据的完整性包括
>
> ①正确性：数据的合法性；
>
> ②有效性：数据规定的有效范围；
>
> ③相容性：描述同一实体各数据保持一致性，DB完整性。
>
> 以上三点性质关系到数据是否正确、有效以及一致。

### 3.数据库系统的构成与类型

一个典型数据库系统构成包括：数据库、数据库管理系统、应用程序、用户（含DBA）四个部分。

![img](D:\SoftWare\YouDaoNoteCache\weixinobU7VjoqcR-OcVQxk1nACiHYgirs\6f9dac57ea5c4640938db9e5a246cc5d\clipboard.png)

#### 3.1数据库系统的类型

##### 3.1.1集中式数据库系统

集中式结构是指一台主机带有多个用户中断的数据库系统，终端只是主机的扩展（显示屏），非独立的计算机。且终端不能完成任何操作，完全依赖主机。如超市收银终端设备。

##### 3.1.2C/S及B/S数据库系统

client/server评分系统

broswer/server跑在浏览器

在客户机/服务器结构中，采用“功能分布”原则，将业务分解成多个子任务，由多态客户机完成。客户端完成数据的表示、处理和用户结构功能，服务器端完成DBMS的核心功能。客户请求服务、服务器提供服务的处理方式是现有常用的新型网络数据库应用模式。

![img](D:\SoftWare\YouDaoNoteCache\weixinobU7VjoqcR-OcVQxk1nACiHYgirs\c99e1ce37d9f4e94a05606a7bcc79aae\clipboard.png)

##### 3.1.3分布式数据库系统

数据具有地区（结点）分布且“逻辑整体性”的特点，由计算机网络、数据库和多个结点构成，使用时如同一个集中式数据库。如分布在不同区域的大型银行等采用的数据库。

![img](D:\SoftWare\YouDaoNoteCache\weixinobU7VjoqcR-OcVQxk1nACiHYgirs\ff6d0f73c48f44328ebb6baf80b17667\clipboard.png)

##### 3.1.4并行式数据库系统

使用多个CPU和多个磁盘进行并行操作，提高数据处理和I/O速度。并行处理时，许多操作同时进行。

![img](D:\SoftWare\YouDaoNoteCache\weixinobU7VjoqcR-OcVQxk1nACiHYgirs\e8e816f5cc734ae78d8469886c0fe17d\clipboard.png)

#### 3.2数据库系统的模式与结构

##### 3.2.1数据模式与型

数据模型是对某类实体（事物）的结构、特征（属性）和约束（要求）的描述。

型是对某类实体（事物）的结构和特征（属性）具体描述（如表头）。

值是型的一个具体值，如货物数据的型定义为为（货物编号、名称、型号、颜色、价格）成为记录型，而（K0001，服装，XXL，黑色，299）则是该记录型的一个记录值。

*模式只涉及型的描述，而不涉及具体值。某数据模式下的一组具体的数据值成为数据模式的一个实例。

![img](D:\SoftWare\YouDaoNoteCache\weixinobU7VjoqcR-OcVQxk1nACiHYgirs\20c4c53703c34621b32a174592571a07\clipboard.png)

##### 3.2.2三级模式结构

（1）外模式

称为子模式或用户模式、外视图，用于描述数据库数据的局部逻辑结构和特征。

（2）模式

称为逻辑模式、概念模式或概念视图，是数据库中所有数据的整体逻辑结构和特征的描述，各数据库只有一个，如E-R图。

（3）内模式

称为内视图或存储模式，在三级模式结构中最内层，即与实际存储的数据方式有关的一层，是数据在数据库内部的表示方式，详细描述了数据复杂的物理结构和存储方式，由多个存储记录组成，不用关心具体的存储位置，如存储文件。

*三级模式结构的优点

1）三级模式结构是数据库系统最本质的系统结构

2）数据共享

3）简化是用户接口（交互）

4）数据安全

##### 3.2.3数据库系统的二级映像

数据的独立性由DBMS的二级映像功能实现，分为物理独立性和逻辑独立性两种。物理独立性指数据的物理结构（包括存储结构、存取方式）的改变，如更换存储设备或物理存储、改变存取方式都不影响数据库的逻辑结构。逻辑独立性指数据的总体逻辑结构改变时，如修改数据模式、改变数据间的练习等，不需修改相应应用程序。

1）外模式/模式映像

位于外部和概念级之间，用于定义外模式和概念模式之间的对应性。数据库中的统一模式可以有任意多个外模式，对于每一个外模式，都存在一个外模式/模式映像。

2）模式/内模式映像

位于概念级和内部之间，用于定义概念模式和内模式之间的对应性。数据库中的模式和内模式都只有一个，所以这种映像是唯一的。确定了数据的全局逻辑与存储结构之间的对应关系。

小结：

1）数据库系统的主要特点有哪些？

主要特点：

①数据统一管理控制和规范

②数据整体结构化

③数据高共享低冗余易扩充

④数据独立性高且程序维护便利

⑤数据完整性和安全性高

⑥保证数据一致性

2）数据库系统的构成和种类？

典型数据库系统构成包括：数据库、数据库管理系统、应用程序、用户（含DBA）四个部分。

种类：集中式数据库系统、C/S及B/S数据库系统、分布式数据库系统、并行式数据库系统。

3）数据库系统的模式结构？

三种数据库系统的模式：外模式、模式、内模式

外模式：称为子模式或用户模式、外视图，用于描述数据库数据的局部逻辑结构和特征。

模式：称为逻辑模式、概念模式或概念视图，是数据库中所有数据的整体逻辑结构和特征的描述，各数据库只有一个，如E-R图。

内模式：称为内视图或存储模式，在三级模式结构中最内层，即与实际存储的数据方式有关的一层，是数据在数据库内部的表示方式，详细描述了数据复杂的物理结构和存储方式，由多个存储记录组成，不用关心具体的存储位置，如存储文件。

*三级模式结构的优点

1）三级模式结构是数据库系统最本质的系统结构

2）数据共享

3）简化是用户接口（交互）

4）数据安全

### 4.数据模型

#### 4.1数据模型的概念和类型

##### 4.1.1三个阶段

数据从客观现实进入到数据库（存储计算机）经历三个阶段：客观现实世界阶段、信息世界阶段和机器世界阶段，也称为数据的三个范畴。

![img](D:\SoftWare\YouDaoNoteCache\weixinobU7VjoqcR-OcVQxk1nACiHYgirs\59e1978d753c460fa029b0abc1547797\clipboard.png)

1）现实世界，是客观存在的事物（实体）及联系。

2）信息世界，是对现实世界的认识和抽象描述，按用户的观点对数据和信息进行建模（概念模型E-R图）

![img](D:\SoftWare\YouDaoNoteCache\weixinobU7VjoqcR-OcVQxk1nACiHYgirs\77219dff0e4f411b9c43beee1dbac565\clipboard.png)

3）机器世界，建立在计算机上的数据模型，以计算机系统的观点进行数据建模（逻辑模型），如关系模型——课程二维表。

数据模型概念：是一种表示数据结构特征的抽象模型，是数据处理的关键和基础，用于抽象、表示和处理现实世界中数据的工具，DBMS的实现都建立在数据模型基础上。

##### 4.1.2数据模型组成三要素

由数据结构、数据操作和完整性约束（数据约束条件）三个基本部分组成，称为数据模型的三要素。

![img](D:\SoftWare\YouDaoNoteCache\weixinobU7VjoqcR-OcVQxk1nACiHYgirs\85613f3f975b4f32b41b5e8b95ecf8ef\clipboard.png)

##### 4.1.3数据模型的类型

根据不同应用，将模型分为三类：

1）概念模型，也称为信息模型，位于客观现实世界与机器世界之间，只用于描述某个特定机构，实现数据在计算机中表示的转换，是一种独立于计算机系统的数据模型。

2）逻辑模（结构）模型，包括网状模型、层次模型和关系模型等以计算机系统的观点对数据建模，是直接面向数据库逻辑结构，是对客观现实世界的第二层抽象，这类模型直接与DBMS有关。

3）物理模型，面向数据处理存储设备物理表示的模型，描述数据在存储介质的组织结构，如存储位置和方式、索引等。

1-2-2概念模型的相关概念及表示

1、概念模型的相关概念

1）实体的相关概念

- - 实体：是现实世界中可以相互区别的事物或活动。
  - 实体集：是同类实体的集合。
  - 实体型：是对同类实体的共有特征的抽象定义。
  - 实体值：是符合实体型定义的，对一个实体的具体描述。

2）联系的相关概念

- - 联系：实体之间的相互关系
  - 联系集：同类联系的集合
  - 联系型：对同类联系的共有特征的抽象定义
  - 联系值：同类联系型确定的某个联系的具体值

*与实体有关概念类似，联系、联系集、联系型、联系值等概念也常统称为联系。

3）属性、键、主属性和域

- - 属性：是描述实体或联系中的一种特征（性），一个实体或联系通常具有多个（项）特征，需要多个相应属性来描述。
  - 键：称码、关键字、关键码等，是属性中可对实体值唯一标识。
  - 主属性：实体中用于键的属性，否则称为非主属性。
  - 域：实体中相应属性的取值范围。

4）联系分类

指两个实体型（含联系型在内）之间的联系的类别。

- - 1对1联系，简记为1：1。
  - 1对多联系，简记为1：n。
  - 多对多联系，简记为m：n。

#### 4.2概念模型的表示方法

1976年陈平山提出实体联系模型，亦称为E-R模型或E-R图（或实体-联系方法），是描述事物（实体）及其联系的概念模型。

##### 4.2.1E-R模型的基本构建

E-R模型是一种用图形表示实体及其联系的方法，所用的图形构建（元件）表示包括：矩形、菱形、椭圆形和连线。矩形表示实体，框内写实体名；椭圆形表示属性，框内写属性名；连线表示实体、联系与属性之间的所属关系或实体与联系之间的相连关系。

##### 4.2.2实体联系的E-R图表示

实体之间的三种联系包括：1对1、1对多、多对多。

![img](D:\SoftWare\YouDaoNoteCache\weixinobU7VjoqcR-OcVQxk1nACiHYgirs\c19042bd0f1f40b0b5a0f259e2316688\clipboard.png)

#### 4.3常用的逻辑模型概述

逻辑模型又称为逻辑结构模型，主要有6种：

- 层次模型
- 网状模型
- 关系模型
- 面向对象模型
- 对象关系模型
- 半结构化模型

1）层次模型结构及特点

是一个树状结构模型，有且只有一个根节点，其余节点为其子孙；每个节点（除根节点外）只有一个父节点（也称为双亲节点），却可以有一个或多个子节点，当然也将无子节点被称为叶；每个节点对应一个记录型，即对应概念模型中的一个实体型，每对节点的父子联系隐含1对多（含1对1）的联系。

![img](D:\SoftWare\YouDaoNoteCache\weixinobU7VjoqcR-OcVQxk1nACiHYgirs\101bdae9a2f64477824a017d839f3731\clipboard.png)

2）网状模型结构及特点

是一个网状结构模型，对层次模型的扩展，允许有多个结点无双亲，同时也允许一个结点有多个双金。层次模型为网状模型的一种最简单状况。

网状模型也有型和值的区别：型是抽象的、静态的、相对稳定不变的；值是具体的、动态的、且需要经常变化的。
