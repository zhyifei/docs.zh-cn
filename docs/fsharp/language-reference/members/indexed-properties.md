---
title: 索引属性 (F#)
description: '了解有关 F # 编制索引的属性提供对有序数据的类似数组的访问权限的属性。'
ms.date: 05/16/2016
ms.openlocfilehash: e56e4e2ea3f35df4c8ec46012357242cb6ce69f3
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43749588"
---
# <a name="indexed-properties"></a>索引属性

*索引属性*提供类似数组的访问权限的属性排序数据。 它们分为三种形式：

* `Item`
* `Ordinal`
* `Cardinal`

F # 成员必须具有名称以提供类似数组的访问这三个名称之一。 `IndexerName` 用于表示任何以下三个选项：

## <a name="syntax"></a>语法

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.IndexerName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.IndexerName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.IndexerName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.IndexerName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a>备注

上述语法中的窗体演示如何定义具有这两者的索引的属性`get`和一个`set`方法中，有`get`方法，或具有`set`方法仅。 此外可以将两者合并为仅限获取和组，所示的语法所示的语法，并生成具有 get 和 set 的属性。 这后一种形式，可将不同的可访问性修饰符和属性放在 get 和 set 方法。

当*IndexerName*是`Item`，编译器会将属性视为默认索引属性。 一个*的默认索引属性*是一个属性，可以访问的对象实例上使用的类似数组的语法。 例如，如果`obj`是用于定义此属性，该语法的类型的对象`obj.[index]`用于访问属性。

用于访问非默认索引属性的语法是提供属性和在括号中的索引的名称。 例如，如果该属性是`Ordinal`，您编写`obj.Ordinal(index)`来访问它。

无论使用哪种形式，您应始终使用为扩充的形式`set`索引属性的方法。 扩充函数有关的信息，请参阅[函数](../functions/index.md)。

## <a name="example"></a>示例

下面的代码示例演示定义和使用的默认和非默认索引的属性具有 get 和 set 方法。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>输出

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a>通过多个索引变量的索引的属性

索引的属性可以具有多个索引变量。 在这种情况下，变量用逗号分隔时使用的属性。 在此类属性中的 set 方法必须具有两个扩充的参数，其中第一个是包含密钥的元组和第二个是要设置的值。

下面的代码演示如何将具有多个索引变量的索引属性。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]

## <a name="see-also"></a>请参阅

- [成员](index.md)
