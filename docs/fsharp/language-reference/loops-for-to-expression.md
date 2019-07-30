---
title: 循环：for...to 表达式
description: F#请参阅to expression 用于在循环变量的一系列值中循环访问循环。
ms.date: 05/16/2016
ms.openlocfilehash: 910c04aa4ea6b2c637dcad147347c1c317b5e0c0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626624"
---
# <a name="loops-forto-expression"></a>循环：for...to 表达式

`for...to`表达式用于在循环变量的一系列值上循环访问循环。

## <a name="syntax"></a>语法

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>备注

标识符的类型从*开始*和*结束*表达式的类型推断而来。 这些表达式的类型必须是32位整数。

尽管从技术上讲`for...to` , 表达式更像是命令式编程语言中的传统语句。 *主体表达式*的返回类型必须为`unit`。 下面的示例演示了`for...to`表达式的各种用法。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

上述代码的输出结果如下。

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
- [循环`for...in`表达式](loops-for-in-expression.md)
- [循环`while...do`表达式](loops-while-do-expression.md)
