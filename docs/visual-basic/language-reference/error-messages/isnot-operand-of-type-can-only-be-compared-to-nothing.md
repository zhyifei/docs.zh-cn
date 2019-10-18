---
title: 类型“typename”的操作数“IsNot”只能与“Nothing”比较，因为“typename”是一个可以为 null 的类型
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 06dc6f1532fecefba4e507bd0cc24aadc936d137
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524367"
---
# <a name="isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a><span data-ttu-id="d7511-102">类型“typename”的操作数“IsNot”只能与“Nothing”比较，因为“typename”是一个可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="d7511-102">'IsNot' operand of type 'typename' can only be compared to 'Nothing', because 'typename' is a nullable type</span></span>

<span data-ttu-id="d7511-103">已将声明为可以为 null 的变量与 `Nothing` 使用 `IsNot` 运算符的表达式进行比较。</span><span class="sxs-lookup"><span data-stu-id="d7511-103">A variable declared as nullable has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>

<span data-ttu-id="d7511-104">**错误 ID：** BC32128</span><span class="sxs-lookup"><span data-stu-id="d7511-104">**Error ID:** BC32128</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d7511-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d7511-105">To correct this error</span></span>

<span data-ttu-id="d7511-106">要将可以为 null 的类型和表达式进行比较（而不是使用 `Nothing` 运算符比较 `IsNot` ），请调用可以为 null 的类型中的 `GetType` 方法并将结果与表达式进行比较，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="d7511-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>

```vb
Dim number? As Integer = 5

If number IsNot Nothing Then
  If number.GetType() IsNot Type.GetType("System.Int32") Then

  End If
End If
```

## <a name="see-also"></a><span data-ttu-id="d7511-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7511-107">See also</span></span>

- [<span data-ttu-id="d7511-108">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="d7511-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="d7511-109">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="d7511-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
