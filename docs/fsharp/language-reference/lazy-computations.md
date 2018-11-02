---
title: 延迟计算 (F#)
description: '了解 F # 迟缓计算如何提高应用程序和库的性能。'
ms.date: 05/16/2016
ms.openlocfilehash: 8afe815f26978de96291a52973d54a9dbcc5eaf2
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "45698203"
---
# <a name="lazy-computations"></a>延迟计算

*延迟计算*都不会立即开始，但改为计算时所需结果的计算。 这可以帮助提高代码的性能。

## <a name="syntax"></a>语法

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>备注

在上述语法中，*表达式*是仅时结果是必需的将计算的代码并*标识符*是将结果存储的值。 值为类型[ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489)，其中的实际类型用于`'T`根据表达式的结果。

延迟计算，可通过限制到仅需要结果时这种情况下计算的执行，从而提高性能。

若要强制执行计算，则调用方法`Force`。 `Force` 将导致执行要执行仅一次。 对后续调用`Force`返回相同的结果，但不是执行任何代码。

下面的代码演示使用惰性计算和使用`Force`。 在此代码的类型`result`是`Lazy<int>`，并`Force`方法将返回`int`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

延迟计算，但不是`Lazy`类型，还可用于序列。 有关详细信息，请参阅[序列](sequences.md)。

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
- [LazyExtensions 模块](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
