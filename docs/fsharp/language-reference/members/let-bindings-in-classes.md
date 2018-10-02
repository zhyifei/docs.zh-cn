---
title: 类中的 let 绑定 (F#)
description: '了解如何通过在类定义中使用 let 绑定定义私有字段和 F # 类的私有函数。'
ms.date: 05/16/2016
ms.openlocfilehash: 237eb98a57571a21c9187abf31f05160374cf4fc
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2018
ms.locfileid: "48033215"
---
# <a name="let-bindings-in-classes"></a>类中的 let 绑定

可以通过使用定义私有字段和 F # 类的私有函数`let`类定义中的绑定。

## <a name="syntax"></a>语法

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a>备注

类标题和继承声明之后的任何成员定义之前，会显示前面的语法。 语法是这样的`let`外部类，但在类中定义的名称的绑定具有作用域限制到类。 一个`let`绑定创建的私有字段或函数; 若要公开的数据或函数公开，声明一个属性或成员方法。

一个`let`绑定，它不是静态调用实例`let`绑定。 实例`let`创建对象时将执行绑定。 静态`let`绑定是类，该类可保证执行之前首先使用的类型的静态初始值设定项的一部分。

实例中的代码`let`绑定可以使用主构造函数的参数。

属性和可访问性修饰符不在允许`let`类中的绑定。

下面的代码示例演示了几种类型的`let`类中的绑定。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

输出如下所示。

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a>创建字段的替代方法

此外可以使用`val`关键字创建的私有字段。 当使用`val`关键字，该字段没有指定值，该对象创建的但改为使用默认值初始化时。 有关详细信息，请参阅[显式字段： val 关键字](explicit-fields-the-val-keyword.md)。

可以使用成员定义和添加关键字，还定义一个类的私有字段`private`到定义。 这很有用，如果您希望更改而无需重新编写代码的成员的可访问性。 有关详细信息，请参阅[访问控制](../access-control.md)。

## <a name="see-also"></a>请参阅

- [成员](index.md)
- [类中的 `do` 绑定](do-bindings-in-classes.md)
- [`let` 绑定](../functions/let-bindings.md)
