---
title: '&#39;是&#39;需要操作数具有引用类型，但此操作数具有值类型&#39; &lt;typename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: 07838e62bd6b180f7dece79355ea7aa1d6c4527a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585575"
---
# <a name="39is39-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-39lttypenamegt39"></a><span data-ttu-id="4c6fd-102">&#39;是&#39;需要操作数具有引用类型，但此操作数具有值类型&#39; &lt;typename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="4c6fd-102">&#39;Is&#39; requires operands that have reference types, but this operand has the value type &#39;&lt;typename&gt;&#39;</span></span>
<span data-ttu-id="4c6fd-103">`Is`比较运算符确定是否两个对象变量引用同一个实例。</span><span class="sxs-lookup"><span data-stu-id="4c6fd-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="4c6fd-104">此比较不为值类型定义。</span><span class="sxs-lookup"><span data-stu-id="4c6fd-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="4c6fd-105">**错误 ID:** BC30020</span><span class="sxs-lookup"><span data-stu-id="4c6fd-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4c6fd-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="4c6fd-106">To correct this error</span></span>  
  
-   <span data-ttu-id="4c6fd-107">使用适当的算术比较运算符或`Like`运算符比较两个值类型。</span><span class="sxs-lookup"><span data-stu-id="4c6fd-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c6fd-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c6fd-108">See Also</span></span>  
 [<span data-ttu-id="4c6fd-109">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="4c6fd-109">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="4c6fd-110">Like 运算符</span><span class="sxs-lookup"><span data-stu-id="4c6fd-110">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="4c6fd-111">比较运算符</span><span class="sxs-lookup"><span data-stu-id="4c6fd-111">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
