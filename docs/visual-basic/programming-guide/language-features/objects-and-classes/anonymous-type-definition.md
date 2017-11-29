---
title: "匿名类型定义 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8b5b7eba55d719c1482b7224ecffc78b776feb00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-type-definition-visual-basic"></a><span data-ttu-id="51d0a-102">匿名类型定义 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51d0a-102">Anonymous Type Definition (Visual Basic)</span></span>
<span data-ttu-id="51d0a-103">在响应的匿名类型的实例声明时，编译器将创建包含类型的指定的属性的新类定义。</span><span class="sxs-lookup"><span data-stu-id="51d0a-103">In response to the declaration of an instance of an anonymous type, the compiler creates a new class definition that contains the specified properties for the type.</span></span>  
  
## <a name="compiler-generated-code"></a><span data-ttu-id="51d0a-104">编译器生成的代码</span><span class="sxs-lookup"><span data-stu-id="51d0a-104">Compiler-Generated Code</span></span>  
 <span data-ttu-id="51d0a-105">以下定义`product`，编译器将创建一个包含属性的新类定义`Name`， `Price`，和`OnHand`。</span><span class="sxs-lookup"><span data-stu-id="51d0a-105">For the following definition of `product`, the compiler creates a new class definition that contains properties `Name`, `Price`, and `OnHand`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#25](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_1.vb)]  
  
 <span data-ttu-id="51d0a-106">类定义包含类似于下面的属性定义。</span><span class="sxs-lookup"><span data-stu-id="51d0a-106">The class definition contains property definitions similar to the following.</span></span> <span data-ttu-id="51d0a-107">请注意，没有任何`Set`键属性的方法。</span><span class="sxs-lookup"><span data-stu-id="51d0a-107">Notice that there is no `Set` method for the key properties.</span></span> <span data-ttu-id="51d0a-108">键属性的值是只读的。</span><span class="sxs-lookup"><span data-stu-id="51d0a-108">The values of key properties are read-only.</span></span>  
  
```vb  
Public Class $Anonymous1  
    Private _name As String  
    Private _price As Double  
    Private _onHand As Integer  
     Public ReadOnly Property Name() As String  
        Get  
            Return _name  
        End Get  
    End Property  
  
    Public ReadOnly Property Price() As Double  
        Get  
            Return _price  
        End Get  
    End Property  
  
    Public Property OnHand() As Integer  
        Get  
            Return _onHand  
        End Get  
        Set(ByVal Value As Integer)  
            _onHand = Value  
        End Set  
    End Property  
  
End Class  
```  
  
 <span data-ttu-id="51d0a-109">此外，匿名类型定义包含一个默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="51d0a-109">In addition, anonymous type definitions contain a default constructor.</span></span> <span data-ttu-id="51d0a-110">不允许使用需要参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="51d0a-110">Constructors that require parameters are not permitted.</span></span>  
  
 <span data-ttu-id="51d0a-111">类型定义匿名类型声明包含至少一个键属性，如果将继承自的三个成员重写<xref:System.Object>: <xref:System.Object.Equals%2A>， <xref:System.Object.GetHashCode%2A>，和<xref:System.Object.ToString%2A>。</span><span class="sxs-lookup"><span data-stu-id="51d0a-111">If an anonymous type declaration contains at least one key property, the type definition overrides three members inherited from <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="51d0a-112">如果不声明了任何键属性，仅<xref:System.Object.ToString%2A>被重写。</span><span class="sxs-lookup"><span data-stu-id="51d0a-112">If no key properties are declared, only <xref:System.Object.ToString%2A> is overridden.</span></span> <span data-ttu-id="51d0a-113">重写提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="51d0a-113">The overrides provide the following functionality:</span></span>  
  
-   <span data-ttu-id="51d0a-114">`Equals`返回`True`如果两个匿名类型实例相同的实例，或者如果只要满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="51d0a-114">`Equals` returns `True` if two anonymous type instances are the same instance, or if they meet the following conditions:</span></span>  
  
    -   <span data-ttu-id="51d0a-115">它们具有相同数量的属性。</span><span class="sxs-lookup"><span data-stu-id="51d0a-115">They have the same number of properties.</span></span>  
  
    -   <span data-ttu-id="51d0a-116">属性声明中相同的顺序，具有相同名称和相同的推断类型。</span><span class="sxs-lookup"><span data-stu-id="51d0a-116">The properties are declared in the same order, with the same names and the same inferred types.</span></span> <span data-ttu-id="51d0a-117">名称比较不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="51d0a-117">Name comparisons are not case-sensitive.</span></span>  
  
    -   <span data-ttu-id="51d0a-118">至少一个属性是键属性，与`Key`关键字应用于相同的属性。</span><span class="sxs-lookup"><span data-stu-id="51d0a-118">At least one of the properties is a key property, and the `Key` keyword is applied to the same properties.</span></span>  
  
    -   <span data-ttu-id="51d0a-119">比较每个相对应的键属性对返回`True`。</span><span class="sxs-lookup"><span data-stu-id="51d0a-119">Comparison of each corresponding pair of key properties returns `True`.</span></span>  
  
     <span data-ttu-id="51d0a-120">例如，在以下示例中，`Equals`返回`True`仅为`employee01`和`employee08`。</span><span class="sxs-lookup"><span data-stu-id="51d0a-120">For example, in the following examples, `Equals` returns `True` only for `employee01` and `employee08`.</span></span> <span data-ttu-id="51d0a-121">前面每行指定为什么不匹配的新实例的原因的注释`employee01`。</span><span class="sxs-lookup"><span data-stu-id="51d0a-121">The comment before each line specifies the reason why the new instance does not match `employee01`.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#24](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_2.vb)]  
  
-   <span data-ttu-id="51d0a-122">`GetHashcode`提供的适当唯一 GetHashCode 算法。</span><span class="sxs-lookup"><span data-stu-id="51d0a-122">`GetHashcode` provides an appropriately unique GetHashCode algorithm.</span></span> <span data-ttu-id="51d0a-123">该算法使用仅键的属性来计算哈希代码。</span><span class="sxs-lookup"><span data-stu-id="51d0a-123">The algorithm uses only the key properties to compute the hash code.</span></span>  
  
-   <span data-ttu-id="51d0a-124">`ToString`返回连接的属性值的字符串，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="51d0a-124">`ToString` returns a string of concatenated property values, as shown in the following example.</span></span> <span data-ttu-id="51d0a-125">将包含密钥和非键属性。</span><span class="sxs-lookup"><span data-stu-id="51d0a-125">Both key and non-key properties are included.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#29](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_3.vb)]  
  
 <span data-ttu-id="51d0a-126">匿名类型的显式命名的属性不能与这些生成的方法冲突。</span><span class="sxs-lookup"><span data-stu-id="51d0a-126">Explicitly named properties of an anonymous type cannot conflict with these generated methods.</span></span> <span data-ttu-id="51d0a-127">也就是说，不能使用`.Equals`， `.GetHashCode`，或`.ToString`以 name 属性。</span><span class="sxs-lookup"><span data-stu-id="51d0a-127">That is, you cannot use `.Equals`, `.GetHashCode`, or `.ToString` to name a property.</span></span>  
  
 <span data-ttu-id="51d0a-128">包含至少一个匿名类型定义的键属性还实现<xref:System.IEquatable%601?displayProperty=nameWithType>接口，其中`T`是匿名类型的类型。</span><span class="sxs-lookup"><span data-stu-id="51d0a-128">Anonymous type definitions that include at least one key property also implement the <xref:System.IEquatable%601?displayProperty=nameWithType> interface, where `T` is the type of the anonymous type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51d0a-129">匿名类型声明中，它们出现在同一程序集中、 其属性具有相同名称和相同的推断类型、 属性的声明的相同顺序和相同的属性标记为键属性时，才会创建同一匿名类型。</span><span class="sxs-lookup"><span data-stu-id="51d0a-129">Anonymous type declarations create the same anonymous type only if they occur in the same assembly, their properties have the same names and the same inferred types, the properties are declared in the same order, and the same properties are marked as key properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51d0a-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51d0a-130">See Also</span></span>  
 [<span data-ttu-id="51d0a-131">匿名类型</span><span class="sxs-lookup"><span data-stu-id="51d0a-131">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="51d0a-132">如何：推断匿名类型声明中的属性名和类型</span><span class="sxs-lookup"><span data-stu-id="51d0a-132">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
