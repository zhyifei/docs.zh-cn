---
title: 代码格式设置准则 (F#)
description: 'F # 编程语言中的以提高可读性，美感、 标准化，并编译了解代码缩进格式设置准则。'
ms.date: 05/16/2016
ms.openlocfilehash: 5bb1f9958a21beb795f9174e44f24c7194453fc3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="code-formatting-guidelines"></a>代码格式设置准则

本主题概述 F # 代码缩进指南。 因为 F # 语言的换行符和缩进影响，不是只需可读性问题、 美观问题或编码的标准化问题以正确格式，你的代码。 你必须设置正确为其正确编译代码的格式。


## <a name="general-rules-for-indentation"></a>缩进的一般规则
需要缩进时，你必须使用空间，不是制表符。 需要至少一个空格。 您的组织可以创建编码标准来指定要用于缩进; 的空格数典型的缩进的出现位置的每个级别的缩进的三个或四个空格。 你可以配置 Visual Studio 以通过更改中的选项根据你的组织的缩进标准`Options`对话框中，可从`Tools`菜单。 在`Text Editor`节点，展开`F#`，然后单击`Tabs`。 有关可用选项的说明，请参阅[选项、 文本编辑器、 所有语言、 选项卡](https://msdn.microsoft.com/library/7sffa753.aspx)。

一般情况下，当编译器分析你的代码，这样可保持内部堆栈，该值指示当前的嵌套级别。 当代码缩进时，一个新的嵌套级别创建，或推送到此内部堆栈上。 一种构造结束时，将弹出级别。 缩进是一种方法来指示级别的末尾，并弹出内部堆栈的方式，但某些令牌还会导致级别弹出，如`end`关键字，或者右大括号或右括号。

多行的构造，如类型定义中中的代码的函数定义`try...with`构造，和循环构造，必须是相对于缩进的构造的开始行。 首行缩进建立同一构造中的后续代码的列位置。 缩进级别称为*上下文*。 中的列位置设置最小列中，称为*越位线*，后面是相同的上下文中的代码行。 遇到的代码行时即比此建立的列位置的更少缩进，编译器假定上下文已结束，并且，你在现在编码在下一步的级别，在以前的上下文中。 术语*越位*用于描述在其中的代码行触发构造结束，因为它不会缩进程度的条件。 换而言之，越位线左侧的代码处于越位位置。 在正确缩进代码中，你利用越位规则以描绘构造的末尾。 如果使用了不正确的缩进，则越位情况可能会导致编译器发出警告，或可能导致你的代码的不正确解释。

越位线确定，如下所示。


- `=`与关联的令牌`let`引入越位线之后的第一个标记列`=`登录。


- 在`if...then...else`表达式，后面的第一个标记的列位置`then`关键字或`else`关键字引入越位线。


- 在`try...with`表达式，后面的第一个标记`try`引入越位线。


- 在`match`表达式，后面的第一个标记`with`和在每行后的第一个标记`->`引入越位线。


- 后面的第一个标记`with`类型中扩展引入越位线。


- 在左大括号或圆括号，或之后的第一个标记`begin`关键字，引入越位线。


- 在关键字中的第一个字符`let`， `if`，和`module`引入越位线。


下面的代码示例阐释的缩进规则。 在这里，print 语句依赖于将其与合适的上下文关联的缩进。 每次切换缩进，上下文将弹出，并返回到以前的上下文。 因此，在每次迭代; 末尾打印一个空格"已完成 ！" 只会打印一次，因为越位缩进建立它不是循环的一部分。 打印"顶级上下文"不是字符串的函数的一部分。 因此，它将打印首先，在静态初始化期间调用该函数之前。

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet1.fs)]

输出如下所示。

```
Top-level context

(Negative number) Zero 1 2 3 Done!
```

当在中断较长的行时, 必须比封闭构造缩进的行延续。 例如，函数自变量必须缩进比第一个字符的函数名称，如下面的代码中所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet2.fs)]

下一节中所述，有例外这些规则。


## <a name="indentation-in-modules"></a>模块中的缩进
本地模块中的代码必须缩进相对于该模块，但顶级模块中的代码不一定要缩进。 Namespace 元素无需进行缩进。

下面的代码示例说明这一点。

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet3.fs)]
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet4.fs)]

有关详细信息，请参阅[模块](modules.md)。


## <a name="exceptions-to-the-basic-indentation-rules"></a>基本的缩进规则的例外
一般规则上, 一节中所述是多行构造中的代码，必须相对于构造的第一行的缩进缩进和第一个越位线发生时由确定构造的末尾。 有关上下文结束时，某些构造，如规则的例外`try...with`表达式，`if...then...else`表达式，以及如何使用`and`语法来声明相互递归函数或类型，具有多个部分。 如后面的部分中，缩进`then`和`else`中`if...then...else`表达式，在同一级别作为令牌与表达式开头，而不是，该值指示结束到上下文，它表示相同的上下文的下一部分。 因此，`if...then...else`可以写入表达式，如下面的代码示例所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet5.fs)]

越位规则的例外仅适用于`then`和`else`关键字。 因此，尽管这不是错误缩进`then`和`else`进一步，失败中的代码行缩进`then`块生成警告。 下面的代码行对此进行了阐释。

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet6.fs)]
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet7.fs)]

中的代码`else`块，其他特殊规则适用。 在前面的示例才会出现警告中的代码`then`块中，未对中的代码`else`块。 这使您可以编写一个函数开头的各种情况检查而不进行强制函数，这可能是中的代码的其余部分的代码`else`块，缩进。 因此，你可以编写以下代码而不会生成一个警告。

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet8.fs)]

另一种例外上下文结束时行缩进距离与上一行是对于中缀运算符，如规则`+`和`|>`。 允许以中缀运算符开头的行开始`(1 + oplength)`列而不会触发上下文，结束的正常位置之前其中`oplength`构成运算符的字符数。 这将导致触发 after 运算符，确保它与上一行的第一个标记。

例如，在下面的代码中，`+`允许符号是小于上一行的缩进的两个列。

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet9.fs)]

尽管随着的嵌套级别变得更高版本，通常会增加缩进，有一些编译器允许你重置为较低的列位置的缩进的下列几种构造。

允许重置的列位置的构造如下所示：


- 匿名函数的主体。 在下面的代码中，打印的表达式在远离比左侧列位置开始`fun`关键字。 但是，行必须启动在开始之前的缩进级别的左边的列 (即，左侧`L`中`List`)。
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet10.fs)]

- 构造括在圆括号或通过`begin`和`end`中`then`或`else`块`if...then...else`表达式，提供缩进是不小于的列位置`if`关键字。 此异常使得在其中的编码样式左括号或`begin`后的行的末尾使用`then`或`else`。


- 主体的模块、 类、 接口和结构由分隔`begin...end`， `{...}`， `class...end`，或`interface...end`。 这样可在其中打开关键字类型定义的类型名称与同一行而不进行强制整个正文要比期初关键字缩进样式。
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet13.fs)]


## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)
