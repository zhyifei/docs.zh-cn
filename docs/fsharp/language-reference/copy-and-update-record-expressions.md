---
title: 复制和更新记录表达式
description: 了解如何编写复制和更新表达式，用于将复制的现有记录或匿名的记录，更新指定的字段，并返回更新的记录或匿名记录。
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: d16f5ca337047ab2eecc8828b21d8a423bf39a1f
ms.sourcegitcommit: c4dfe37032c64a1fba2cc3d5947550d79f95e3b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041741"
---
# <a name="copy-and-update-record-expressions"></a>复制和更新记录表达式

一个*复制和更新记录表达式*一个表达式，将复制的现有记录、 更新指定的字段，并返回已更新的记录。

## <a name="syntax"></a>语法

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a>备注

记录和匿名记录是默认情况下，固定不变，这样可能是不会更新到现有记录。 若要创建已更新的记录的记录的所有字段将需要再次指定。 若要简化此任务*复制并更新表达式*可用。 此表达式采用现有记录，通过使用指定的表达式的字段和由表达式指定的缺失字段创建一个新的相同的类型。

您需要复制现有记录，并可能更改的某些字段值时，这很有用。

需要对实例的新创建的记录。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

如果您打算更新仅在您可以使用该记录的字段*复制和更新记录表达式*如下所示：

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>请参阅

- [记录](records.md)
- [匿名的记录](anonymous-records.md)
- [F# 语言参考](index.md)
