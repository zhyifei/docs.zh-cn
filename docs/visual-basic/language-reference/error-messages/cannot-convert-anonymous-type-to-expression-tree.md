---
title: 无法将匿名类型转换为表达式树，因为它包含用于初始化另一个字段的字段
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c2cf8a40060359393807cfb648c46fef9ed853af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a><span data-ttu-id="f794b-102">无法将匿名类型转换为表达式树，因为它包含用于初始化另一个字段的字段</span><span class="sxs-lookup"><span data-stu-id="f794b-102">Cannot convert anonymous type to expression tree because it contains a field that is used in the initialization of another field</span></span>
<span data-ttu-id="f794b-103">当匿名类型的一个属性用于初始化匿名类型的另一个属性时，编译器不接受的匿名为表达式树的转换。</span><span class="sxs-lookup"><span data-stu-id="f794b-103">The compiler does not accept conversion of an anonymous to an expression tree when one property of the anonymous type is used to initialize another property of the anonymous type.</span></span> <span data-ttu-id="f794b-104">例如，在下面的代码中，`Prop1`是声明的初始化列表中，然后用作的初始值`Prop2`。</span><span class="sxs-lookup"><span data-stu-id="f794b-104">For example, in the following code, `Prop1` is declared in the initialization list and then used as the initial value for `Prop2`.</span></span>  
  
```vb  
Module M2  
  
    Sub ExpressionExample(Of T)(ByVal x As Expressions.Expression(Of Func(Of T)))  
    End Sub  
  
    Sub Main()  
        ' The following line causes the error.  
        ' ExpressionExample(Function() New With {.Prop1 = 2, .Prop2 = .Prop1})  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="f794b-105">**错误 ID:** BC36548</span><span class="sxs-lookup"><span data-stu-id="f794b-105">**Error ID:** BC36548</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f794b-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="f794b-106">To correct this error</span></span>  
  
-   <span data-ttu-id="f794b-107">分配的初始值`Prop1`到本地变量。</span><span class="sxs-lookup"><span data-stu-id="f794b-107">Assign the initial value for `Prop1` to a local variable.</span></span> <span data-ttu-id="f794b-108">将该变量分配到同时`Prop1`和`Prop2`，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="f794b-108">Assign that variable to both `Prop1` and `Prop2`, as shown in the following code.</span></span>  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f794b-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f794b-109">See Also</span></span>  
 [<span data-ttu-id="f794b-110">匿名类型</span><span class="sxs-lookup"><span data-stu-id="f794b-110">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="f794b-111">表达式树</span><span class="sxs-lookup"><span data-stu-id="f794b-111">Expression Trees</span></span>](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)  
 [<span data-ttu-id="f794b-112">如何：使用表达式树来生成动态查询</span><span class="sxs-lookup"><span data-stu-id="f794b-112">How to: Use Expression Trees to Build Dynamic Queries</span></span>](http://msdn.microsoft.com/library/1e37e0cc-eef3-48bb-8b69-3adabf322735)
