---
title: "方法的 &#39;System.Nullable (Of T) &#39;不能用作的操作数 &#39;AddressOf &#39;运算符"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords: BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ce0e9bc6abd71f22e3f6c3486ef40493e74d820f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="methods-of-39systemnullableof-t39-cannot-be-used-as-operands-of-the-39addressof39-operator"></a><span data-ttu-id="ea804-102">方法的 &#39;System.Nullable (Of T) &#39;不能用作的操作数 &#39;AddressOf &#39;运算符</span><span class="sxs-lookup"><span data-stu-id="ea804-102">Methods of &#39;System.Nullable(Of T)&#39; cannot be used as operands of the &#39;AddressOf&#39; operator</span></span>
<span data-ttu-id="ea804-103">语句使用`AddressOf`运算符的操作数，表示的过程与<xref:System.Nullable%601>结构。</span><span class="sxs-lookup"><span data-stu-id="ea804-103">A statement uses the `AddressOf` operator with an operand that represents a procedure of the <xref:System.Nullable%601> structure.</span></span>  
  
 <span data-ttu-id="ea804-104">**错误 ID:** BC32126</span><span class="sxs-lookup"><span data-stu-id="ea804-104">**Error ID:** BC32126</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ea804-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ea804-105">To correct this error</span></span>  
  
-   <span data-ttu-id="ea804-106">中的过程名称替换`AddressOf`子句的操作数不是的成员， <xref:System.Nullable%601>。</span><span class="sxs-lookup"><span data-stu-id="ea804-106">Replace the procedure name in the `AddressOf` clause with an operand that is not a member of <xref:System.Nullable%601>.</span></span>  
  
-   <span data-ttu-id="ea804-107">编写包装的方法的类<xref:System.Nullable%601>你想要使用。</span><span class="sxs-lookup"><span data-stu-id="ea804-107">Write a class that wraps the method of <xref:System.Nullable%601> that you want to use.</span></span> <span data-ttu-id="ea804-108">在下面的示例中，`NullableWrapper`类定义一个名为的新方法`GetValueOrDefault`。</span><span class="sxs-lookup"><span data-stu-id="ea804-108">In the following example, the `NullableWrapper` class defines a new method named `GetValueOrDefault`.</span></span> <span data-ttu-id="ea804-109">因为此新方法不是成员的<xref:System.Nullable%601>，它可以应用于`nullInstance`，可以为 null 的类型，以形成的自变量的实例`AddressOf`。</span><span class="sxs-lookup"><span data-stu-id="ea804-109">Because this new method is not a member of <xref:System.Nullable%601>, it can be applied to `nullInstance`, an instance of a nullable type, to form an argument for `AddressOf`.</span></span>  
  
```vb  
Module Module1  
  
    Delegate Function Deleg() As Integer  
  
    Sub Main()  
        Dim nullInstance As New Nullable(Of Integer)(1)  
  
        Dim del As Deleg  
  
        ' GetValueOrDefault is a method of the Nullable generic  
        ' type. It cannot be used as an operand of AddressOf.  
        ' del = AddressOf nullInstance.GetValueOrDefault  
  
        ' The following line uses the GetValueOrDefault method  
        ' defined in the NullableWrapper class.  
        del = AddressOf (New NullableWrapper(  
            Of Integer)(nullInstance)).GetValueOrDefault  
  
        Console.WriteLine(del.Invoke())  
    End Sub  
  
    Class NullableWrapper(Of T As Structure)  
        Private m_Value As Nullable(Of T)  
  
        Sub New(ByVal Value As Nullable(Of T))  
            m_Value = Value  
        End Sub  
  
        Public Function GetValueOrDefault() As T  
            Return m_Value.Value  
        End Function  
    End Class  
End Module  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea804-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea804-110">See Also</span></span>  
 <xref:System.Nullable%601>  
 [<span data-ttu-id="ea804-111">AddressOf 运算符</span><span class="sxs-lookup"><span data-stu-id="ea804-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="ea804-112">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="ea804-112">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="ea804-113">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="ea804-113">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
