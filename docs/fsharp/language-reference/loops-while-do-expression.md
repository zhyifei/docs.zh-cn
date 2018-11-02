---
title: 循环：while...do 表达式 (F#)
description: 请参阅如何...执行表达式用于在指定的测试条件为 true 时执行迭代操作 （循环）。
ms.date: 05/16/2016
ms.openlocfilehash: 5cf4461669221f91cb50e238c25494f03a10bbc2
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "45664704"
---
# <a name="loops-whiledo-expression"></a>循环：while...do 表达式

`while...do`表达式用于在指定的测试条件为 true 时执行迭代操作 （循环）。

## <a name="syntax"></a>语法

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>备注

*测试表达式*计算; 如果`true`，则*正文表达式*执行和重新评估测试表达式。 *正文表达式*必须具有类型`unit`。 如果测试表达式是`false`，在迭代结束。

下面的示例演示如何使用`while...do`表达式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

上述代码的输出是介于 1 和 20 之间的随机数的流的最后一个是 10。

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE]
可以使用`while...do`在序列表达式和其他计算表达式，这种情况下的自定义的版本`while...do`使用表达式。 有关详细信息，请参阅[序列](sequences.md)，[异步工作流](asynchronous-workflows.md)，并[计算表达式](computation-expressions.md)。

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
- [循环：`for...in` 表达式](loops-for-in-expression.md)
- [循环：`for...to` 表达式](loops-for-to-expression.md)
