---
title: "只能从不带自变量的简单名或限定名中推断匿名类型成员名称"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords: BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7068928a17ee5fdb7bf6b5e0a40aaa7e5ef32f11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="33526-102">只能从不带自变量的简单名或限定名中推断匿名类型成员名称</span><span class="sxs-lookup"><span data-stu-id="33526-102">Anonymous type member name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="33526-103">无法推断的复杂表达式中的匿名类型成员名称。</span><span class="sxs-lookup"><span data-stu-id="33526-103">You cannot infer an anonymous type member name from a complex expression.</span></span>  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 <span data-ttu-id="33526-104">有关源从中匿名类型可以和不能推断成员名称和类型的详细信息，请参阅[如何： 推断属性名和匿名类型声明中的类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)。</span><span class="sxs-lookup"><span data-stu-id="33526-104">For more information about sources from which anonymous types can and cannot infer member names and types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
 <span data-ttu-id="33526-105">**错误 ID:** BC36556</span><span class="sxs-lookup"><span data-stu-id="33526-105">**Error ID:** BC36556</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="33526-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="33526-106">To correct this error</span></span>  
  
-   <span data-ttu-id="33526-107">为成员名称，分配表达式，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="33526-107">Assign the expression to a member name, as shown in the following code:</span></span>  
  
    ```  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="33526-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33526-108">See Also</span></span>  
 [<span data-ttu-id="33526-109">匿名类型</span><span class="sxs-lookup"><span data-stu-id="33526-109">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="33526-110">如何：推断匿名类型声明中的属性名和类型</span><span class="sxs-lookup"><span data-stu-id="33526-110">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
