---
title: '&#39;IsNot&#39;类型的操作数&#39;typename&#39;仅可以相比&#39;执行任何操作&#39;，这是因为&#39;typename&#39;为 null 的类型'
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 44cc17c73b476e5e322b9b58b021bc7bcd63167f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587591"
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a><span data-ttu-id="00916-102">&#39;IsNot&#39;类型的操作数&#39;typename&#39;仅可以相比&#39;执行任何操作&#39;，这是因为&#39;typename&#39;为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="00916-102">&#39;IsNot&#39; operand of type &#39;typename&#39; can only be compared to &#39;Nothing&#39;, because &#39;typename&#39; is a nullable type</span></span>
<span data-ttu-id="00916-103">声明为可以为 null 的变量进行了比较表达式以外`Nothing`使用`IsNot`运算符。</span><span class="sxs-lookup"><span data-stu-id="00916-103">A variable declared as nullable has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>  
  
 <span data-ttu-id="00916-104">**错误 ID:** BC32128</span><span class="sxs-lookup"><span data-stu-id="00916-104">**Error ID:** BC32128</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="00916-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="00916-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="00916-106">要比较表达式为 null 的类型以外`Nothing`使用`IsNot`运算符，请调用`GetType`可以为 null 的类型和比较结果与表达式，如下面的示例中所示的方法。</span><span class="sxs-lookup"><span data-stu-id="00916-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="00916-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="00916-107">See Also</span></span>  
 [<span data-ttu-id="00916-108">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="00916-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="00916-109">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="00916-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
