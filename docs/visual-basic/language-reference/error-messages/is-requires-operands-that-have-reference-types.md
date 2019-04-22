---
title: “Is”要求具有引用类型的操作数，但此操作数的值类型为“<typename>”。
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: b828de196a12128a9f34ee1f9ff1e57fee22c687
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843846"
---
# <a name="is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a><span data-ttu-id="6a04b-102">Is 要求具有引用类型的操作数，但此操作数具有值类型\<类型名称 ></span><span class="sxs-lookup"><span data-stu-id="6a04b-102">'Is' requires operands that have reference types, but this operand has the value type '\<typename>'</span></span>
<span data-ttu-id="6a04b-103">`Is`比较运算符确定两个对象变量是否引用同一个实例。</span><span class="sxs-lookup"><span data-stu-id="6a04b-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="6a04b-104">对于值类型未定义此比较。</span><span class="sxs-lookup"><span data-stu-id="6a04b-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="6a04b-105">**错误 ID:** BC30020</span><span class="sxs-lookup"><span data-stu-id="6a04b-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6a04b-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="6a04b-106">To correct this error</span></span>  
  
-   <span data-ttu-id="6a04b-107">使用适当的算术比较运算符或`Like`运算符比较两个值类型。</span><span class="sxs-lookup"><span data-stu-id="6a04b-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a04b-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a04b-108">See also</span></span>

- [<span data-ttu-id="6a04b-109">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="6a04b-109">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="6a04b-110">Like 运算符</span><span class="sxs-lookup"><span data-stu-id="6a04b-110">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="6a04b-111">比较运算符</span><span class="sxs-lookup"><span data-stu-id="6a04b-111">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
