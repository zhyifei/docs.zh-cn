---
title: '复制和更新记录的表达式 （F #）'
description: 了解如何编写的复制和更新记录表达式复制现有的记录，更新指定的字段，并返回已更新的记录。
author: ChrSteinert
ms.author: phcart
ms.date: 06/04/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 98a515b5f053e9339588157185848e8315a580f4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="copy-and-update-record-expressions"></a>复制和更新记录表达式

A*复制和更新记录表达式*是复制现有记录，更新指定的字段，并返回已更新的记录的表达式。


## <a name="syntax"></a>语法

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a>备注
记录是默认情况下，不可变的因此可能是不会更新到现有记录。 若要创建的记录的所有字段的更新的记录将不得不再次指定。 为了简化此任务*复制和更新记录表达式*可用。 此表达式采用现有记录，以通过使用表达式中的指定的字段和缺少的字段指定的表达式创建一个新的相同的类型。
当你需要复制现有记录，并可能会更改某些字段值时，这很有用。

以为例新创建的记录。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

如果要仅在你可以使用该记录的字段上更新*复制和更新记录表达式*类似于以下：

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>请参阅
[记录](records.md)

[F# 语言参考](index.md)
