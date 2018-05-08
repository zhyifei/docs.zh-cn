---
title: 延迟计算 (F#)
description: '了解如何 F # 延迟计算可以提高应用程序和库的性能。'
ms.date: 05/16/2016
ms.openlocfilehash: 1c4eb6ab247c44a04a9d145185e2de7ec01b8e0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="lazy-computations"></a>延迟计算

*延迟计算*是不立即计算的值，但需要结果时，将改为计算的计算。 这可以帮助提高你的代码的性能。

## <a name="syntax"></a>语法

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>备注

在上述语法中，*表达式*是仅当结果是必需的时, 计算的代码和*标识符*是将结果存储的值。 值的类型是[ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489)，其中的实际类型用于`'T`取决于该表达式的结果。

延迟计算使您能够通过限制为仅需要结果时这种情况下计算执行改进性能。

若要强制要执行的计算，则调用方法`Force`。 `Force` 会导致将仅执行一次执行。 后续调用`Force`返回相同的结果，但不是执行任何代码。

下面的代码演示延迟计算的使用和的`Force`。 在此代码中的一种`result`是`Lazy<int>`，和`Force`方法返回`int`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

迟缓计算中，但不是`Lazy`类型，也可以用来序列。 有关详细信息，请参阅[序列](sequences.md)。

## <a name="see-also"></a>请参阅

[F# 语言参考](index.md)

[LazyExtensions 模块](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
