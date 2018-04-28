---
title: 断言 (F#)
description: '了解如何在 F # 编程语言测试表达式断言表达式用作一种调试功能。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 195b4a34977a63d92559003b5cd0bb89490a1e7a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="assertions"></a>断言

`assert`表达式是一种调试功能，可用于测试表达式。 在调试模式中遇到故障时，断言将生成一个系统错误对话框。

## <a name="syntax"></a>语法

```fsharp
assert condition
```

## <a name="remarks"></a>备注

`assert`表达式具有类型`bool -> unit`。

在上述语法中，*条件*表示将要测试的布尔表达式。 如果表达式计算结果为`true`，执行会继续不受影响。 如果其计算结果为`false`，则会生成系统的错误对话框。 错误对话框中具有的标题中包含字符串**断言失败**。 对话框中包含堆栈跟踪，该值指示出现了断言失败。

在调试模式下; 编译时，才会启用断言检查也就是说，如果常量`DEBUG`定义。 在项目系统中，默认情况下，`DEBUG`调试配置中但不是在发布配置定义常量。

断言失败错误不能捕获了使用 F # 异常处理。

>[!NOTE]
`assert`函数将解析为<xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>。

## <a name="example"></a>示例

下面的代码示例演示如何使用`assert`表达式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]
    
## <a name="see-also"></a>请参阅

[F# 语言参考](index.md)
