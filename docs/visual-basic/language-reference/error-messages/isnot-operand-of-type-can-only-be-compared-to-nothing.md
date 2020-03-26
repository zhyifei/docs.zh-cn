---
title: 类型“typename”的操作数“IsNot”只能与“Nothing”比较，因为“typename”是一个可以为 null 的类型
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 1660971e2a1a11d7a2d14f222cd149edf4aa4c7b
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249508"
---
# <a name="isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a><span data-ttu-id="767ed-102">类型“typename”的操作数“IsNot”只能与“Nothing”比较，因为“typename”是一个可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="767ed-102">'IsNot' operand of type 'typename' can only be compared to 'Nothing', because 'typename' is a nullable type</span></span>

<span data-ttu-id="767ed-103">声明为空值类型的变量已与使用`Nothing``IsNot`运算符以外的表达式进行比较。</span><span class="sxs-lookup"><span data-stu-id="767ed-103">A variable declared as a nullable value type has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>

<span data-ttu-id="767ed-104">**错误 ID：** BC32128</span><span class="sxs-lookup"><span data-stu-id="767ed-104">**Error ID:** BC32128</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="767ed-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="767ed-105">To correct this error</span></span>

<span data-ttu-id="767ed-106">要将可以为 null 的类型和表达式进行比较（而不是使用 `Nothing` 运算符比较 `IsNot` ），请调用可以为 null 的类型中的 `GetType` 方法并将结果与表达式进行比较，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="767ed-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>

```vb
Dim number? As Integer = 5

If number IsNot Nothing Then
  If number.GetType() IsNot Type.GetType("System.Int32") Then

  End If
End If
```

## <a name="see-also"></a><span data-ttu-id="767ed-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="767ed-107">See also</span></span>

- [<span data-ttu-id="767ed-108">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="767ed-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="767ed-109">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="767ed-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
