---
title: Of 子句 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: c0cfbb5109d5b49f995028944e735c96440c9ab2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583508"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="9e9e3-102">Of 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e9e3-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="9e9e3-103">引入 `Of` 子句，该子句标识*泛型*类、结构、接口、委托或过程中的*类型参数*。</span><span class="sxs-lookup"><span data-stu-id="9e9e3-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="9e9e3-104">有关泛型类型的信息，请参阅[Visual Basic 中的泛型类型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)。</span><span class="sxs-lookup"><span data-stu-id="9e9e3-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="9e9e3-105">使用关键字 of</span><span class="sxs-lookup"><span data-stu-id="9e9e3-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="9e9e3-106">下面的代码示例使用 `Of` 关键字定义带有两个类型参数的类的轮廓。</span><span class="sxs-lookup"><span data-stu-id="9e9e3-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="9e9e3-107">它通过 <xref:System.IComparable> 接口*限制*`keyType` 参数，这意味着使用的代码必须提供实现 <xref:System.IComparable> 的类型参数。</span><span class="sxs-lookup"><span data-stu-id="9e9e3-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="9e9e3-108">这是必需的，以便 `add` 过程可以调用 <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="9e9e3-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9e9e3-109">有关约束的详细信息，请参阅 [Type List](../../../visual-basic/language-reference/statements/type-list.md)。</span><span class="sxs-lookup"><span data-stu-id="9e9e3-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
```vb  
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
  
 <span data-ttu-id="9e9e3-110">如果你完成了前面的类定义，则可以从它构造各种 `dictionary` 类。</span><span class="sxs-lookup"><span data-stu-id="9e9e3-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="9e9e3-111">您提供的用于 `entryType` 和 `keyType` 确定类的项类型以及它与每个项关联的键的类型。</span><span class="sxs-lookup"><span data-stu-id="9e9e3-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="9e9e3-112">由于约束，你必须提供以 `keyType` 实现 <xref:System.IComparable> 的类型。</span><span class="sxs-lookup"><span data-stu-id="9e9e3-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="9e9e3-113">下面的代码示例创建一个对象，该对象保存 `String` 项，并将 `Integer` 键与每个项关联。</span><span class="sxs-lookup"><span data-stu-id="9e9e3-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="9e9e3-114">`Integer` 实现 <xref:System.IComparable>，因此满足 `keyType` 的约束。</span><span class="sxs-lookup"><span data-stu-id="9e9e3-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="9e9e3-115">`Of` 关键字可用于以下上下文中：</span><span class="sxs-lookup"><span data-stu-id="9e9e3-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="9e9e3-116">Class 语句</span><span class="sxs-lookup"><span data-stu-id="9e9e3-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="9e9e3-117">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="9e9e3-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="9e9e3-118">Function 语句</span><span class="sxs-lookup"><span data-stu-id="9e9e3-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="9e9e3-119">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="9e9e3-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="9e9e3-120">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="9e9e3-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="9e9e3-121">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="9e9e3-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="9e9e3-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e9e3-122">See also</span></span>

- <xref:System.IComparable>
- [<span data-ttu-id="9e9e3-123">类型列表</span><span class="sxs-lookup"><span data-stu-id="9e9e3-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="9e9e3-124">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e9e3-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="9e9e3-125">In</span><span class="sxs-lookup"><span data-stu-id="9e9e3-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="9e9e3-126">Out</span><span class="sxs-lookup"><span data-stu-id="9e9e3-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
