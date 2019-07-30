---
title: 断言
description: 了解如何使用 "assert" 表达式作为F#编程语言中的测试表达式的调试功能。
ms.date: 05/16/2016
ms.openlocfilehash: b8b7e9662143b432d650f87515d4af31cced4149
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630034"
---
# <a name="assertions"></a>断言

`assert`表达式是一种可用于测试表达式的调试功能。 在调试模式中遇到故障时，断言将生成一个系统错误对话框。

## <a name="syntax"></a>语法

```fsharp
assert condition
```

## <a name="remarks"></a>备注

表达式`assert`的类型`bool -> unit`为。

在前面的语法中, *condition*表示要测试的布尔表达式。 如果表达式的计算结果`true`为, 则继续不受影响。 如果计算结果为`false`, 则会生成系统错误对话框。 错误对话框的标题包含字符串**断言失败**。 该对话框包含一个堆栈跟踪, 指示断言失败发生的位置。

仅当在调试模式下进行编译时, 才启用断言检查;也就是说, 如果定义了常数`DEBUG` 。 在项目系统中, 默认情况下, `DEBUG`常量在调试配置中定义, 而不是在发布配置中定义。

使用F#异常处理无法捕获断言失败错误。

> [!NOTE]
> 函数解析为<xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>。 `assert`

## <a name="example"></a>示例

下面的代码示例演示如何使用`assert`表达式。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
