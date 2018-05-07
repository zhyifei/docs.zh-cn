---
title: 循环：for...to 表达式 (F#)
description: '请参阅如何 F # 为..表达式用于在循环中循环访问一系列的循环变量的值。'
ms.date: 05/16/2016
ms.openlocfilehash: 841c7d557abc11e0253cb87ab8081cc77671b44b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="loops-forto-expression"></a>循环：for...to 表达式

`for...to`表达式用于在循环中循环访问一系列的循环变量的值。


## <a name="syntax"></a>语法

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>备注
标识符的类型推断的一种从*启动*和*完成*表达式。 这些表达式的类型必须是 32 位整数。

尽管从技术上讲的表达式，`for...to`是更像在命令性编程语言中的传统语句。 返回类型*主体表达式*必须`unit`。 下面的示例演示的各种用法`for...to`表达式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

上述代码的输出结果如下。

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)

[循环：`for...in` 表达式](loops-for-in-expression.md)

[循环：`while...do` 表达式](loops-while-do-expression.md)
