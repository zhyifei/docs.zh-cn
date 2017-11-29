---
title: "Of 子句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- Of
- vb.Of
- vb.of
helpviewer_keywords:
- Of keyword [Visual Basic]
- arguments [Visual Basic], data types
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ef3ac4ac88727b1dcae50fa14abde03f29a16fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="fc02a-102">Of 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc02a-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="fc02a-103">引入了`Of`子句，用于标识*类型参数*上*泛型*类、 结构、 接口、 委托或过程。</span><span class="sxs-lookup"><span data-stu-id="fc02a-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="fc02a-104">泛型类型的信息，请参阅[Visual Basic 中的泛型类型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)。</span><span class="sxs-lookup"><span data-stu-id="fc02a-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="fc02a-105">使用的关键字</span><span class="sxs-lookup"><span data-stu-id="fc02a-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="fc02a-106">下面的代码示例使用`Of`关键字来定义轮廓的采用两个类型参数的类。</span><span class="sxs-lookup"><span data-stu-id="fc02a-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="fc02a-107">它*约束*`keyType`参数<xref:System.IComparable>接口，这意味着使用的代码必须提供一个类型参数，实现<xref:System.IComparable>。</span><span class="sxs-lookup"><span data-stu-id="fc02a-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="fc02a-108">这是必需的以便`add`过程可以调用<xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="fc02a-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fc02a-109">约束的详细信息，请参阅[类型列表](../../../visual-basic/language-reference/statements/type-list.md)。</span><span class="sxs-lookup"><span data-stu-id="fc02a-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
```  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 <span data-ttu-id="fc02a-110">如果完成前面的类定义，您可以构造各种`dictionary`从它的类。</span><span class="sxs-lookup"><span data-stu-id="fc02a-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="fc02a-111">提供给类型`entryType`和`keyType`确定哪种类型的条目类包含和哪种类型的密钥，它将关联的每一项。</span><span class="sxs-lookup"><span data-stu-id="fc02a-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="fc02a-112">由于存在约束，则你必须提供给`keyType`实现的类型<xref:System.IComparable>。</span><span class="sxs-lookup"><span data-stu-id="fc02a-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="fc02a-113">下面的代码示例创建包含的对象`String`条目并将关联`Integer`与每个密钥。</span><span class="sxs-lookup"><span data-stu-id="fc02a-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="fc02a-114">`Integer`实现<xref:System.IComparable>并且因此上满足约束`keyType`。</span><span class="sxs-lookup"><span data-stu-id="fc02a-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="fc02a-115">`Of` 关键字可用于以下上下文中：</span><span class="sxs-lookup"><span data-stu-id="fc02a-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="fc02a-116">Class 语句</span><span class="sxs-lookup"><span data-stu-id="fc02a-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="fc02a-117">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="fc02a-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="fc02a-118">Function 语句</span><span class="sxs-lookup"><span data-stu-id="fc02a-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="fc02a-119">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="fc02a-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="fc02a-120">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="fc02a-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="fc02a-121">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="fc02a-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="fc02a-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc02a-122">See Also</span></span>  
 <xref:System.IComparable>  
 [<span data-ttu-id="fc02a-123">类型列表</span><span class="sxs-lookup"><span data-stu-id="fc02a-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="fc02a-124">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="fc02a-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="fc02a-125">In</span><span class="sxs-lookup"><span data-stu-id="fc02a-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [<span data-ttu-id="fc02a-126">Out</span><span class="sxs-lookup"><span data-stu-id="fc02a-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
