---
title: 类型缩写 (F#)
description: '了解有关 F # 类型缩写，以使代码更易于读取为指定类型的更有意义的名称。'
ms.date: 05/16/2016
ms.openlocfilehash: 259cd6c84e22fc7c98e08255d3e0ded5b87af352
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44176765"
---
# <a name="type-abbreviations"></a>类型缩写

一个*类型缩写*是别名或备用名称的类型。

## <a name="syntax"></a>语法

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a>备注

类型缩写可用于为指定类型的更有意义的名称，以使代码易于阅读。 此外可以使用它们创建易于使用为原本不方便，写出的类型名称。此外，可以使用类型缩写来轻松地更改基础类型，而无需更改使用类型的所有代码。 下面是简单类型缩写。

类型缩写的可访问性默认为`public`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

类型缩写可以包含泛型参数，如以下代码所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

在前面的代码，`Transform`是表示任何类型的一个自变量的函数的类型缩写，将返回相同类型的单个值。

类型缩写不会保留在.NET Framework MSIL 代码。 因此，当你使用另一种.NET Framework 语言中的 F # 程序集时，必须使用类型缩写的基础类型名称。

此外可以上度量单位的使用类型缩写。 有关详细信息，请参阅[度量单位](units-of-measure.md)。

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
