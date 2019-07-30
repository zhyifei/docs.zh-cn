---
title: 延迟表达式
description: 了解懒惰F#表达式如何提高应用程序和库的性能。
ms.date: 03/13/2019
ms.openlocfilehash: 97429e9a4c3838cbaa2ead197db4443e0820e8b3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630748"
---
# <a name="lazy-expressions"></a>延迟表达式

*惰性表达式*是不会立即计算的表达式, 而是在需要结果时计算的表达式。 这有助于提高代码的性能。

## <a name="syntax"></a>语法

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>备注

在前面的语法中, *expression*是只在需要结果时计算的代码, 而*标识符*是存储结果的值。 值的类型[`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489)为, 其中用于的`'T`实际类型由表达式的结果确定。

利用迟缓表达式, 你可以通过将表达式的执行限制为仅需要结果的情况来提高性能。

若要强制执行表达式, 请调用方法`Force`。 `Force`导致执行只执行一次。 后续调用将`Force`返回相同的结果, 但不执行任何代码。

下面的代码演示了如何使用延迟表达式以及`Force`如何使用。 在此代码中, 的类型`result`为`Lazy<int>`, `int`并且`Force`方法返回。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

迟缓计算 (但不`Lazy`是类型) 也用于序列。 有关详细信息, 请参阅[序列](sequences.md)。

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
- [LazyExtensions 模块](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
