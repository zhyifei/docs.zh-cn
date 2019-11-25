---
title: New 运算符
ms.date: 07/20/2015
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
ms.openlocfilehash: 27b5b4516ef729045036c36fedc24b6c576a4f61
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348317"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="71d7e-102">New 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71d7e-102">New Operator (Visual Basic)</span></span>

<span data-ttu-id="71d7e-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span><span class="sxs-lookup"><span data-stu-id="71d7e-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>

## <a name="remarks"></a><span data-ttu-id="71d7e-104">备注</span><span class="sxs-lookup"><span data-stu-id="71d7e-104">Remarks</span></span>

<span data-ttu-id="71d7e-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span><span class="sxs-lookup"><span data-stu-id="71d7e-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="71d7e-106">This means that the class must expose one or more constructors that the calling code can access.</span><span class="sxs-lookup"><span data-stu-id="71d7e-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>

<span data-ttu-id="71d7e-107">You can use a `New` clause in a declaration statement or an assignment statement.</span><span class="sxs-lookup"><span data-stu-id="71d7e-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="71d7e-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span><span class="sxs-lookup"><span data-stu-id="71d7e-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="71d7e-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter:</span><span class="sxs-lookup"><span data-stu-id="71d7e-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter:</span></span>

[!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]

<span data-ttu-id="71d7e-110">Since arrays are classes, `New` can create a new array instance, as shown in the following example:</span><span class="sxs-lookup"><span data-stu-id="71d7e-110">Since arrays are classes, `New` can create a new array instance, as shown in the following example:</span></span>

[!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]

<span data-ttu-id="71d7e-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span><span class="sxs-lookup"><span data-stu-id="71d7e-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>

> [!NOTE]
> <span data-ttu-id="71d7e-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span><span class="sxs-lookup"><span data-stu-id="71d7e-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="71d7e-113">For more information about type parameters and constraints, see [Type List](../statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="71d7e-113">For more information about type parameters and constraints, see [Type List](../statements/type-list.md).</span></span>

<span data-ttu-id="71d7e-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span><span class="sxs-lookup"><span data-stu-id="71d7e-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="71d7e-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="71d7e-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

<span data-ttu-id="71d7e-116">`New` 关键字可用于以下上下文中：</span><span class="sxs-lookup"><span data-stu-id="71d7e-116">The `New` keyword can be used in these contexts:</span></span>

- [<span data-ttu-id="71d7e-117">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="71d7e-117">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="71d7e-118">Of</span><span class="sxs-lookup"><span data-stu-id="71d7e-118">Of</span></span>](../statements/of-clause.md)
- [<span data-ttu-id="71d7e-119">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="71d7e-119">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="71d7e-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="71d7e-120">See also</span></span>

- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="71d7e-121">关键字</span><span class="sxs-lookup"><span data-stu-id="71d7e-121">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="71d7e-122">类型列表</span><span class="sxs-lookup"><span data-stu-id="71d7e-122">Type List</span></span>](../statements/type-list.md)
- [<span data-ttu-id="71d7e-123">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="71d7e-123">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="71d7e-124">对象生存期：如何创建和销毁对象</span><span class="sxs-lookup"><span data-stu-id="71d7e-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
