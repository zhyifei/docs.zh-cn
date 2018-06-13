---
title: 循环：while...do 表达式 (F#)
description: 请参阅如何时...是否会使用表达式来指定的测试条件为 true 时执行迭代执行 （循环）。
ms.date: 05/16/2016
ms.openlocfilehash: e3198246e44bbb11b226f04da6795f3da22626e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562227"
---
# <a name="loops-whiledo-expression"></a>循环：while...do 表达式

`while...do`会使用表达式来指定的测试条件为 true 时执行迭代执行 （循环）。


## <a name="syntax"></a>语法

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>备注
*测试表达式*计算; 如果它是`true`、*主体表达式*执行和重新计算的测试表达式。 *主体表达式*必须具有类型`unit`。 如果测试表达式为`false`，在迭代结束。

下面的示例演示如何使用`while...do`表达式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

上述代码的输出是其中的最后一个为 10 个介于 1 和 20 之间的随机数的流。

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
你可以使用`while...do`序列表达式和其他计算表达式，在这种情况下的自定义的版本`while...do`使用表达式。 有关详细信息，请参阅[序列](sequences.md)，[异步工作流](asynchronous-workflows.md)，和[计算表达式](computation-expressions.md)。


## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)

[循环：`for...in` 表达式](loops-for-in-expression.md)

[循环：`for...to` 表达式](loops-for-to-expression.md)
