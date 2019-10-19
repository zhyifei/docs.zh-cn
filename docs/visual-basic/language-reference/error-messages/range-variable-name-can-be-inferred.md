---
title: 只能根据不带自变量的简单名称或限定名称推断范围变量名称
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: ca50ddd86cfbba8db0148ed315645714acabc18d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582428"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>只能根据不带自变量的简单名称或限定名称推断范围变量名称

采用一个或多个自变量的编程元素包含在 LINQ 查询中。 编译器无法从该编程元素推断范围变量。

**错误 ID：** BC36599

## <a name="to-correct-this-error"></a>更正此错误

提供编程元素的显式变量名，如下面的代码所示：

```vb
Dim query = From var1 In collection1
            Select VariableAlias= SampleFunction(var1), var1
```

## <a name="see-also"></a>请参阅

- [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)
