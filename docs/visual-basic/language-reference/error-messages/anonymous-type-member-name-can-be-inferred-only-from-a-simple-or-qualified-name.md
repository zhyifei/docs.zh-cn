---
title: 只能从不带自变量的简单名或限定名中推断匿名类型成员名称
ms.date: 07/20/2015
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
ms.openlocfilehash: b798f296b62b51de34a7ec5ce5a8b608273f5748
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819224"
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="57f74-102">只能从不带自变量的简单名或限定名中推断匿名类型成员名称</span><span class="sxs-lookup"><span data-stu-id="57f74-102">Anonymous type member name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="57f74-103">无法推断匿名类型成员名称从复杂的表达式。</span><span class="sxs-lookup"><span data-stu-id="57f74-103">You cannot infer an anonymous type member name from a complex expression.</span></span>  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 <span data-ttu-id="57f74-104">有关匿名类型可以和不能推断成员名称和类型从其源的详细信息，请参阅[如何：推断属性名和匿名类型声明中的类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)。</span><span class="sxs-lookup"><span data-stu-id="57f74-104">For more information about sources from which anonymous types can and cannot infer member names and types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
 <span data-ttu-id="57f74-105">**错误 ID:** BC36556</span><span class="sxs-lookup"><span data-stu-id="57f74-105">**Error ID:** BC36556</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="57f74-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="57f74-106">To correct this error</span></span>  
  
-   <span data-ttu-id="57f74-107">将表达式分配到成员名称，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="57f74-107">Assign the expression to a member name, as shown in the following code:</span></span>  
  
    ```  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="57f74-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="57f74-108">See also</span></span>

- [<span data-ttu-id="57f74-109">匿名类型</span><span class="sxs-lookup"><span data-stu-id="57f74-109">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="57f74-110">如何：推断属性名和匿名类型声明中的类型</span><span class="sxs-lookup"><span data-stu-id="57f74-110">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
