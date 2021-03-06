---
title: 计算机软件测试规范
date: 2019-12-03 22:40:33
tags:
  - testing
  - specification
categories:
  - testing
---

标准号：GB/T 15532-2008 计算机软件测试规范

关联标准

> GB/T 8566 信息技术 软件生存周期过程
>
> GB/T 9386 计算机软件测试文档编制规范
>
> GB/T 11457 信息技术 软件工程术语
>
> GB/T 16260.1 软件工程 产品质量 第一部分：质量模型
>
> GB/T 18492 信息技术 系统及软件完整性级别
>
> GB/T 20158 信息技术 软件生存周期过程 配置管理

# 测试目的

计算机软件的测试目的是：

1. 验证软件是否满足软件开发合同或项目开发计划、系统/子系统设计文档、软件需求规格说明、软件设计说明和软件产品说明等规定的软件质量要求；
2. 通过测试，发现软件缺陷；
3. 为软件产品的质量测量和评价提供依据。

# 测试类别

根据 GB/T 8566 的要求，本标准对如下测试类别做详细描述：

1. 单元测试；
2. 集成测试；
3. 配置项测试（也称软件合格性测试或确认测试）；
4. 系统测试；
5. 验收测试。

可根据软件的模型、类型、完整性级别选择执行测试类型。

回归测试可出现在上述每个测试类别中，并贯穿于整个软件生存周期，故单独分类进行描述。

# 测试过程

## 概述

软件测试过程一般包括四项活动，按顺序分别是：测试侧或、测试设计、测试执行、测试总结。

## 测试策划

测试策划主要是进行测试需求分析。即确定需要测试的内容或质量特性；确定测试的充分性要求；踢出测试的基本方法；确定测试的资源和技术需求；进行风险分析与评估；制定测试计划（含资源计划和进度计划）。有关测试计划的内容和要求见 GB/T 9386 。

## 测试设计

依据测试需求，分析并选用已有的测试用例或设计新的测试用例；获取并验证测试数据；根据测试资源、风险等约束条件，确定测试用例执行顺序；获取测试资源，开发测试软件；建立并校准测试环境；进行测试就绪评审，主要评审测试计划的合理性和测试用例的正确性、有效性和覆盖充分性，评审测试组织、环境和设备工具是否齐备并符合要求。在进入下一阶段工作之前，应通过测试就绪评审。

<!-- more -->

## 测试执行

执行测试用例，获取测试结果；分析并制定测试结果。同时根据不同的判定结果采取相应的措施；对测试过程的正常或异常终止情况进行核对，并分局核对结果，对未达到测试终止条件的测试用例，决定是停止测试，还是需要修改或补充测试用例集，并进一步测试。

## 测试总结

整理和分析测试数据，评价测试效果和被测软件项，描述测试状态。如，实际测试与测试计划和测试说明的差异、测试充分性分析、未能解决的测试时间等；描述北侧软件项的状态，如，被测软件与需求的差异，发现的软件差错等；最后，完成软件测试报告，并通过测试评审。

# 测试方法

## 静态测试方法

静态测试方法包括检查单和静态分析方法，对文档的静态测试方法主要以检查单的形式进行，而对代码的静态测试方法一般采用代码审查、代码走查和静态分析，静态分析一般包括控制流分析、数据流分析、接口分析和表达式分析。

应对软件代码进行审查、走查或静态分析；对于规模较小、安全性要求很高的代码也可进行形式化证明。

## 动态测试方法

动态测试方法一般采用白盒测试方法和黑盒测试方法。黑盒测试方法一般包裹功能分解、边界值分析、判定表、因果图、状态图、随机测试、猜错法和正交实验法等；白盒测试方法一般包括控制流测试（语句覆盖测试、分支覆盖测试、条件覆盖测试、条件组合覆盖测试、路径覆盖测试）、数据流测试、程序变异、程序插桩、域测试和符号求值等。

在软件动态测试过程中，采用适当的测试方法，实现测试目标。配置项测试和系统测试一般采用黑盒测试方法；集成测试一般主要采用黑盒测试方法，辅助以白盒测试方法；单元测试一般采用白盒测试方法，辅助以黑盒测试方法。

静态测试和动态测试的详细说明参加附录 A。

### 概述

动态测试是建立在程序的执行过程中。根据被测对象内部情况的了解与否，分为黑盒测试和白盒测试。

黑盒测试又称功能测试、数据驱动测试或基于规格说明的测试，这种测试不必了解被测对象的内部情况，而依靠需求规格说明中的功能来设计测试用例。

白盒测试又称结构测试、逻辑测试或基于程序的测试，这种测试应了解程序的内部构造，并根据内部构造设计测试用例。

在单元测试时一般采用白盒测试，在配置项测试或系统测试时一般采用黑盒测试。

### 黑盒测试方法

#### 功能分解

功能分解是将需求规格说明中每一个功能加以分解，确保各个功能被全面地测试。功能分解是一种较常用的方法。

步骤如下：

1. 使用程序设计中的功能抽象方法把程序分解为功能单元；
2. 使用数据抽象方法产生测试每个功能单元的数据。

功能抽象中程序被看成一种抽象的功能层次，每个层次可标识被测试的功能，层次结构中的某一功能由其下一层功能定义。按照功能层次进行分解，可以得到众多的最低层次的子功能，以这些子功能为对象，进行测试用例设计。

数据对象中，数据结构可以由抽象数据类型的层次图来描述，每个抽象数据类型有其取值集合。程序的每一个输入和输出量的取值集合用数据对象来描述。

#### 等价类划分

等价类划分是在分析需求规格说明的基础上，吧程序的输入域划分成若干部分，然后在每部分中选取代表性数据形成测试用例。

步骤如下：

1. 划分有效等价类：对规格说明是有意义、合理的输入数据所构成的集合；
2. 划分无效等价类：对规格说明是无意义、不合理的输入数据所构成的集合；
3. 为每个等价类定义一个唯一的编号；
4. 为每一个等价类设计一组测试用例，确保覆盖相应的等价类。

#### 边界值分析

边界值分析是针对边界值进行测试的。使用等于、小于或大于边界值的数据对程序进行测试的方法就是边界值分析方法。

步骤如下：

1. 通过分析规格说明，找出所有可能的边界条件；
2. 对每一个边界条件，给出满足和不满足边界值的输入数据；
3. 设计相应的测试用例。

对满足边界值的输入可以发现计算差错，对不满足的输入可以发现域差错。该方法会为其他测试方法补充一些测试用例，绝大多数测试都会用到本方法。

#### 判定表

判定表由四部分组成：条件桩、条件条目、动作桩、动作条目。任何一个条件组合的取值及其相应要执行的操作构成规则，条目中的每一列是一条规则。

条件引用输入的等价类，动作引用被测软件的主要功能处理部分，规则就是测试用例。

建立并优化判定表，把判定表中每一列表表示的情况写成测试用例。

该方法的使用有以下要求：

1. 规格说明以判定表形式给出，或是很容易转换成判定表；
2. 条件的排列顺序不会影响执行哪些操作；
3. 桂策的排列顺序不会影响执行哪些操作；
4. 每当某一规则的条件已经满足，并确定要执行的操作后，不必检验别的规则；
5. 如果某一规则得到满足，将执行多个操作，这些操作的执行与顺序无关。

#### 因果图

因果图方法是通过画因果图，把用自然语言描述的功能说明转换为判定表，然后为判定表的每一列设计一个测试用例。

步骤如下：

1. 分析程序规格说明，引出原因（输入条件）和结果（输出结果），并给每一个原因和结果赋予一个标识符；
2. 分析程序规格说明中语义的内容，并将其表示成连接各个原因和各个结果的“因果图”；
3. 在因果图上标明约束条件；
4. 通过跟踪因果图中的状态条件，把因果图转换成有限项的判定表；
5. 把判定表中每一列表示的情况生成测试用例。

如果需求规格说明中含有输入条件的组合，宜采用本方法。有些软件的因果图可能非常庞大，以至于根据因果图得到的测试用例数目非常大，此时不宜使用本方法。

#### 随机测试

随机测试指测试输入数据是所有可能输入值中随机选取的。测试人员只需要规定输入变量的取值区间，在需要时提供必要的变换机制，使产生的随机数服从预期的概率分布。该方法获得预期输出比较困难，多用于可靠性测试和系统强度测试。

#### 猜错法

猜错法是有经验的测试人员，通过列出可能有的差错和易错情况表，写出测试用例的方法。

#### 正交实验法

正交实验法是从大量的实验点中挑出适量的、有代表性的点，应用正交表，合理地安排实验的一种科学的实验设计方法。

利用正交实验法来设计测试用例时，首先要根据被测软件的规格说明书找出影响功能实现的操作对象和外部因素，把它们当做因子，而把各个因子的取值当做状态，生成二元的因素分析表。然后，利用正交表进行各因子的状态组合，构造有效的测试数据集，并由此建立因果图。这样得出的测试用例的数目将大大减少。

### 白盒测试方法

#### 控制流测试

控制流测试依据控制流程图产生测试用例，通过对不同控制结构成分的测试验证程序的控制结构。所谓验证某种控制结构即指使这种控制结构在程序运行中得到执行，也称这一过程为覆盖。以下介绍几种覆盖：

1. 语句覆盖：要求设计适当数量的测试用例，运行被测程序，使得程序中每一条语句至少被执行一次，语句覆盖在测试中主要发现出错语句。
2. 分支覆盖：要求设计适当数量的测试用例，运行被测程序，使得程序中每个真值分支和假值分支至少执行一次，分支覆盖也称判定覆盖。
3. 条件覆盖：要求设计适当数量的测试用例，运行被测程序，使得每个判断中的每个条件的可能取值至少满足一次。
4. 条件组合覆盖：要求设计适当数量的测试用例，运行被测程序，使得每个判断中条件的各种组合至少出现一次，这种方法包含了“分支覆盖”和“条件覆盖”的各种要求。
5. 路径覆盖：要求设计适当数量的测试用例，运行被测程序，使得程序沿所有可能的路径执行，较大程序的路径可能很多，所以在设计测试用例时，要简化循环次数。

以上各种覆盖的控制流测试步骤如下：

1. 将程序流程图转换成控制流图；
2. 经过语法分析求得路径表达式；
3. 生成路径树；
4. 进行路径编码；
5. 经过译码得到执行的路径；
6. 通过路径枚举产生特定路径的测试用例。

#### 数据流测试

数据流测试是用控制流程图对变量的定义和引用进行分析，查找出未定义的变量或定义了未使用的变量，这些变量可能是拼错的变量、变量混淆或丢失了语句。数据流测试一般使用工具进行。

数据流测试通过一定的覆盖准则，检查程序中每个数据对象的每次定义、使用和消除的情况。

数据流测试步骤：

1. 将程序流程图转换成控制流图；
2. 在每个链路上标注对有关变量的数据操作的操作符号和符号序列；
3. 选定数据流测试策略；
4. 根据测试策略得到测试路径；
5. 根据路径可以获得测试输入数据和测试用例。
6. 动态数据流异常检查在程序运行时执行，获得的是对数据对象的真实操作序列，克服了静态分析检查的局限，但动态方式检查是沿着与测试输入有关的一部分路径进行的，检查的全面性和程序结构覆盖有关。

#### 程序变异

一种差错驱动测试，是为了查出被测软件在做过其他测试后还剩余一些的小差错。本方法一般测试工具进行。

#### 程序插桩

程序插桩是向被测程序中插入操作以实现测试目的的方法。程序插桩不应该影响到被测程序的运行过程和功能。

有很多的工具有程序插桩功能。由于数据记录量大，手工进行较为烦琐。

#### 域测试

域测试是要判别程序对输入空间的划分是否正确。该方法限制太多，使用不方便，供有特殊需求的测试使用。

#### 符号求值

符号求值是允许数值变量取“符号值”以及数值。符号求值可以检查公式的执行结果是否达到程序预期的目的；也可以通过程序的符号执行，产生出程序的路径，用于产生测试数据。符号求值最好使用工具，在公式分支较少时手工推到也是可行的。
