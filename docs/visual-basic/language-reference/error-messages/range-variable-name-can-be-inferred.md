---
title: 只能根据不带自变量的简单名称或限定名称推断范围变量名称
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: a0b5633bb0efb3c67f73810552ef9a14ac3d0c70
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331645"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="fd6d0-102">只能根据不带自变量的简单名称或限定名称推断范围变量名称</span><span class="sxs-lookup"><span data-stu-id="fd6d0-102">Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="fd6d0-103">在 LINQ 查询中包含一个或多个参数的编程元素。</span><span class="sxs-lookup"><span data-stu-id="fd6d0-103">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="fd6d0-104">编译器不能推断该编程元素中的某个范围变量。</span><span class="sxs-lookup"><span data-stu-id="fd6d0-104">The compiler is unable to infer a range variable from that programming element.</span></span>  
  
 <span data-ttu-id="fd6d0-105">**错误 ID:** BC36599</span><span class="sxs-lookup"><span data-stu-id="fd6d0-105">**Error ID:** BC36599</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fd6d0-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="fd6d0-106">To correct this error</span></span>  
  
1. <span data-ttu-id="fd6d0-107">提供的编程元素的显式变量名称，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="fd6d0-107">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd6d0-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd6d0-108">See also</span></span>

- [<span data-ttu-id="fd6d0-109">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="fd6d0-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="fd6d0-110">Select 子句</span><span class="sxs-lookup"><span data-stu-id="fd6d0-110">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
