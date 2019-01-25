---
title: '&#39;IsNot&#39;类型的操作数&#39;typename&#39;仅可与比较&#39;Nothing&#39;，因为&#39;typename&#39;为 null 的类型'
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 65b04c85bccd169bbb2eea847d7b8af96c1a292f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505713"
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a><span data-ttu-id="0616b-102">&#39;IsNot&#39;类型的操作数&#39;typename&#39;仅可与比较&#39;Nothing&#39;，因为&#39;typename&#39;为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="0616b-102">&#39;IsNot&#39; operand of type &#39;typename&#39; can only be compared to &#39;Nothing&#39;, because &#39;typename&#39; is a nullable type</span></span>
<span data-ttu-id="0616b-103">声明为可以为 null 的变量进行了比较表达式以外`Nothing`使用`IsNot`运算符。</span><span class="sxs-lookup"><span data-stu-id="0616b-103">A variable declared as nullable has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>  
  
 <span data-ttu-id="0616b-104">**错误 ID:** BC32128</span><span class="sxs-lookup"><span data-stu-id="0616b-104">**Error ID:** BC32128</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0616b-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="0616b-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="0616b-106">要将可以为 null 的类型和表达式进行比较（而不是使用 `Nothing` 运算符比较 `IsNot` ），请调用可以为 null 的类型中的 `GetType` 方法并将结果与表达式进行比较，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="0616b-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="0616b-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="0616b-107">See also</span></span>
- [<span data-ttu-id="0616b-108">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="0616b-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="0616b-109">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="0616b-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
