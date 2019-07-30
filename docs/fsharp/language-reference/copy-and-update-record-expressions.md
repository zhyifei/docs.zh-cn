---
title: 复制和更新记录表达式
description: 了解如何编写一个 "复制和更新表达式", 该表达式复制现有记录或匿名记录, 更新指定字段, 并返回已更新的记录或匿名记录。
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: dfb20a6ff8282ae5988772cc0f0841db23aad942
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630376"
---
# <a name="copy-and-update-record-expressions"></a>复制和更新记录表达式

*复制和更新记录表达式*是一个表达式, 该表达式复制现有记录、更新指定字段并返回已更新的记录。

## <a name="syntax"></a>语法

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a>备注

记录和匿名记录在默认情况下是不可变的, 因此不能更新现有记录。 若要创建更新的记录, 则必须重新指定记录的所有字段。 若要简化此任务, 可以使用*复制和更新表达式*。 此表达式使用现有记录, 通过使用表达式中指定的字段和表达式指定的缺失字段来创建同一类型的新记录。

当必须复制现有记录, 并且可能更改某些字段值时, 这会很有用。

用于实例创建新的记录。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

如果仅更新该记录的字段, 可以使用如下所示的*复制和更新记录表达式*:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>请参阅

- [记录](records.md)
- [匿名记录](anonymous-records.md)
- [F# 语言参考](index.md)
