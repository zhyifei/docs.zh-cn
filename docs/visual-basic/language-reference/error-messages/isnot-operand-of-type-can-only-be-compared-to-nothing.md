---
title: 类型“typename”的操作数“IsNot”只能与“Nothing”比较，因为“typename”是一个可以为 null 的类型
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: be2a3239b2ca520c4051a1504f91a766b4401a05
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834018"
---
# <a name="isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a><span data-ttu-id="39074-102">类型“typename”的操作数“IsNot”只能与“Nothing”比较，因为“typename”是一个可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="39074-102">'IsNot' operand of type 'typename' can only be compared to 'Nothing', because 'typename' is a nullable type</span></span>
<span data-ttu-id="39074-103">声明为可以为 null 的变量进行了比较表达式以外`Nothing`使用`IsNot`运算符。</span><span class="sxs-lookup"><span data-stu-id="39074-103">A variable declared as nullable has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>  
  
 <span data-ttu-id="39074-104">**错误 ID:** BC32128</span><span class="sxs-lookup"><span data-stu-id="39074-104">**Error ID:** BC32128</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="39074-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="39074-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="39074-106">要将可以为 null 的类型和表达式进行比较（而不是使用 `Nothing` 运算符比较 `IsNot` ），请调用可以为 null 的类型中的 `GetType` 方法并将结果与表达式进行比较，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="39074-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="39074-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="39074-107">See also</span></span>

- [<span data-ttu-id="39074-108">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="39074-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="39074-109">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="39074-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
