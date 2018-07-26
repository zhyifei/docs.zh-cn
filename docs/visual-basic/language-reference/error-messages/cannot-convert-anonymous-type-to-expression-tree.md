---
title: 无法将匿名类型转换为表达式树，因为它包含用于初始化另一个字段的字段
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: 2f97a0de74428ce42a088644580a78bf8fd99945
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936797"
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a><span data-ttu-id="1db59-102">无法将匿名类型转换为表达式树，因为它包含用于初始化另一个字段的字段</span><span class="sxs-lookup"><span data-stu-id="1db59-102">Cannot convert anonymous type to expression tree because it contains a field that is used in the initialization of another field</span></span>
<span data-ttu-id="1db59-103">使用匿名类型的一个属性来初始化匿名类型的另一个属性时，编译器不接受匿名的转换为表达式树。</span><span class="sxs-lookup"><span data-stu-id="1db59-103">The compiler does not accept conversion of an anonymous to an expression tree when one property of the anonymous type is used to initialize another property of the anonymous type.</span></span> <span data-ttu-id="1db59-104">例如，在下面的代码中，`Prop1`是声明的初始化列表中，然后用作初始值`Prop2`。</span><span class="sxs-lookup"><span data-stu-id="1db59-104">For example, in the following code, `Prop1` is declared in the initialization list and then used as the initial value for `Prop2`.</span></span>  
  
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
  
 <span data-ttu-id="1db59-105">**错误 ID:** BC36548</span><span class="sxs-lookup"><span data-stu-id="1db59-105">**Error ID:** BC36548</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1db59-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="1db59-106">To correct this error</span></span>  
  
-   <span data-ttu-id="1db59-107">分配的初始值`Prop1`给本地变量。</span><span class="sxs-lookup"><span data-stu-id="1db59-107">Assign the initial value for `Prop1` to a local variable.</span></span> <span data-ttu-id="1db59-108">将该变量分配给这两`Prop1`和`Prop2`，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="1db59-108">Assign that variable to both `Prop1` and `Prop2`, as shown in the following code.</span></span>  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1db59-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="1db59-109">See also</span></span>

[<span data-ttu-id="1db59-110">匿名类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1db59-110">Anonymous Types (Visual Basic)</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
[<span data-ttu-id="1db59-111">表达式树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1db59-111">Expression Trees (Visual Basic)</span></span>](../../programming-guide/concepts/expression-trees/index.md)  
[<span data-ttu-id="1db59-112">如何： 使用表达式树来生成动态查询 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1db59-112">How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)</span></span>](../../programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md)  