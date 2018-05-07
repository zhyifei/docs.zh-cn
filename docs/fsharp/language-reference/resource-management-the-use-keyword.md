---
title: 资源管理：use 关键字 (F#)
description: '了解有关 F # 关键字使用和 using 函数，可以控制的初始化和资源释放。'
ms.date: 05/16/2016
ms.openlocfilehash: c75783080d1d87c6ee75aede500d3d0b3fdf8355
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="resource-management-the-use-keyword"></a>资源管理：use 关键字

本主题介绍关键字`use`和`using`函数，可以控制的初始化和资源释放。

## <a name="resources"></a>资源
术语*资源*以多种方式使用。 是，资源可以是应用程序使用，如字符串、 图形和类似的内容，但在此上下文中的数据*资源*指软件或操作系统资源，例如图形设备上下文，文件句柄、 网络和数据库连接、 并发对象，如等待句柄，依次类推。 由应用程序的这些资源的使用涉及从操作系统或其他资源提供程序，其后是更高版本的资源池，以便它可以提供给另一个应用程序资源的获取。 当应用程序不释放回常见的池的资源时，将发生的问题。

## <a name="managing-resources"></a>管理资源
若要有效地负责任地管理应用程序中的资源，你必须立即和可预测的方式释放资源。 .NET Framework 可帮助你执行此操作通过提供`System.IDisposable`接口。 实现一种`System.IDisposable`具有`System.IDisposable.Dispose`方法，正确地释放资源。 编写良好的应用程序会保证`System.IDisposable.Dispose`时不再需要占用有限的资源的任何对象，立即调用。 幸运的是，大多数.NET 语言都提供支持，以简化这一操作，F # 也不例外。 存在的两个有用的语言构造，支持的释放模式：`use`绑定和`using`函数。

## <a name="use-binding"></a>使用绑定
`use`关键字具有类似于一个窗体`let`绑定：

使用*值* = *表达式*

它提供与相同的功能`let`绑定，但添加对的调用`Dispose`上时的值超出范围的值。 请注意，编译器将插入 null 值，检查，因此，如果值`null`，调用`Dispose`不尝试。

下面的示例演示如何通过使用自动关闭文件`use`关键字。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

>[!NOTE]
你可以使用`use`在计算表达式中，在这种情况下的自定义的版本`use`使用表达式。 有关详细信息，请参阅[序列](sequences.md)，[异步工作流](asynchronous-workflows.md)，和[计算表达式](computation-expressions.md)。


## <a name="using-function"></a>使用函数
`using`函数具有以下形式：

`using` (*expression1*)*函数或 lambda*

在`using`表达式， *expression1*创建必须释放的对象。 结果*expression1* （必须释放的对象） 将成为自变量，*值*到*函数或 lambda*，它是需要单个任一函数剩余的值匹配的类型自变量由*expression1*，或需要该类型的自变量的 lambda 表达式。 在执行函数的末尾，则运行时调用`Dispose`并释放资源 (除非的值是`null`，在这种情况下不尝试对释放的调用)。

下面的示例演示`using`使用 lambda 表达式的表达式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

下面的示例说明`using`使用函数的表达式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

请注意，该函数可以是具有已应用某些参数的函数。 下面的代码示例展示了此操作。 会创建一个文件包含由字符串`XYZ`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

`using`函数和`use`绑定是几乎等效方法完成同样的操作。 `using`关键字提供了更好地控制何时`Dispose`调用。 当你使用`using`，`Dispose`在使用时调用的函数或 lambda 表达式，则末尾`use`关键字，`Dispose`称为包含的代码块的末尾。 一般情况下，您应该会希望使用`use`而不是`using`函数。


## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)
