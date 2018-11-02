---
title: 断言 (F#)
description: '了解如何在 F # 编程语言中测试表达式 assert 表达式用作一种调试功能。'
ms.date: 05/16/2016
ms.openlocfilehash: 85b1e839bfd19bada48b7f1821d15ddd8fa77754
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "48842471"
---
# <a name="assertions"></a>断言

`assert`表达式是一个可用于测试表达式的调试功能。 在调试模式中遇到故障时，断言将生成一个系统错误对话框。

## <a name="syntax"></a>语法

```fsharp
assert condition
```

## <a name="remarks"></a>备注

`assert`表达式具有类型`bool -> unit`。

在上述语法中，*条件*表示是要测试的布尔表达式。 如果表达式计算结果为`true`，执行将继续不受影响。 如果其计算结果为`false`，则会生成系统的错误对话框。 错误对话框中已包含的字符串的标题**断言失败**。 对话框中包含指示出现了断言失败的堆栈跟踪。

在调试模式下; 编译时，才会启用断言检查也就是说，如果常量`DEBUG`定义。 在项目系统中，默认情况下，`DEBUG`常量在调试配置中而不是在发布配置定义。

不能通过使用 F # 异常处理捕获断言失败错误。

>[!NOTE]
`assert`函数将解析为<xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>。

## <a name="example"></a>示例

下面的代码示例演示如何使用`assert`表达式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
