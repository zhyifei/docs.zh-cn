---
title: "&#39; 是 &#39;需要操作数具有引用类型，但此操作数具有值类型 &#39;&lt;typename&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords: BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 28d017a566fdc1e55cb53ce907641d6bccfb354c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39is39-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-39lttypenamegt39"></a><span data-ttu-id="2ab82-102">&#39; 是 &#39;需要操作数具有引用类型，但此操作数具有值类型 &#39;&lt;typename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="2ab82-102">&#39;Is&#39; requires operands that have reference types, but this operand has the value type &#39;&lt;typename&gt;&#39;</span></span>
<span data-ttu-id="2ab82-103">`Is`比较运算符确定是否两个对象变量引用同一个实例。</span><span class="sxs-lookup"><span data-stu-id="2ab82-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="2ab82-104">此比较不为值类型定义。</span><span class="sxs-lookup"><span data-stu-id="2ab82-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="2ab82-105">**错误 ID:** BC30020</span><span class="sxs-lookup"><span data-stu-id="2ab82-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2ab82-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="2ab82-106">To correct this error</span></span>  
  
-   <span data-ttu-id="2ab82-107">使用适当的算术比较运算符或`Like`运算符比较两个值类型。</span><span class="sxs-lookup"><span data-stu-id="2ab82-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab82-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ab82-108">See Also</span></span>  
 [<span data-ttu-id="2ab82-109">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="2ab82-109">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="2ab82-110">Like 运算符</span><span class="sxs-lookup"><span data-stu-id="2ab82-110">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="2ab82-111">比较运算符</span><span class="sxs-lookup"><span data-stu-id="2ab82-111">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
