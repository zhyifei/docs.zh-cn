---
title: "New 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 74f0352379e861ad135ea23d31ea07d638f9e6c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="2eab0-102">New 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2eab0-102">New Operator (Visual Basic)</span></span>
<span data-ttu-id="2eab0-103">引入了`New`子句创建一个新的对象实例，指定类型参数的构造函数约束或标识`Sub`作为类构造函数的过程。</span><span class="sxs-lookup"><span data-stu-id="2eab0-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2eab0-104">备注</span><span class="sxs-lookup"><span data-stu-id="2eab0-104">Remarks</span></span>  
 <span data-ttu-id="2eab0-105">声明或赋值语句中`New`子句必须指定可从中创建实例定义的类。</span><span class="sxs-lookup"><span data-stu-id="2eab0-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="2eab0-106">这意味着类必须公开一个或多个构造函数调用的代码可访问。</span><span class="sxs-lookup"><span data-stu-id="2eab0-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>  
  
 <span data-ttu-id="2eab0-107">你可以使用`New`声明语句或赋值语句中的子句。</span><span class="sxs-lookup"><span data-stu-id="2eab0-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="2eab0-108">当该语句在运行时，它将调用适当的构造函数指定的类，并传递你提供任何参数。</span><span class="sxs-lookup"><span data-stu-id="2eab0-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="2eab0-109">下面的示例演示这通过创建的实例`Customer`具有两个构造函数的类、 一个不带任何参数，另一个采用字符串参数。</span><span class="sxs-lookup"><span data-stu-id="2eab0-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter.</span></span>  
  
 [!code-vb[VbVbalrKeywords#11](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_1.vb)]  
  
 <span data-ttu-id="2eab0-110">由于数组是类，`New`可以创建新的数组实例，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="2eab0-110">Since arrays are classes, `New` can create a new array instance, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrKeywords#12](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_2.vb)]  
  
 <span data-ttu-id="2eab0-111">公共语言运行时 (CLR) 引发<xref:System.OutOfMemoryException>错误是否存在内存不足，无法创建新实例。</span><span class="sxs-lookup"><span data-stu-id="2eab0-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2eab0-112">`New`关键字还用于在类型参数列表中指定所提供的类型必须公开可访问的无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="2eab0-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="2eab0-113">有关类型参数和约束的详细信息，请参阅[类型列表](../../../visual-basic/language-reference/statements/type-list.md)。</span><span class="sxs-lookup"><span data-stu-id="2eab0-113">For more information about type parameters and constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
 <span data-ttu-id="2eab0-114">若要创建一个类的构造函数过程，设置的名称`Sub`过程`New`关键字。</span><span class="sxs-lookup"><span data-stu-id="2eab0-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="2eab0-115">有关详细信息，请参阅[对象生存期： 对象的创建和破坏的方式](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)。</span><span class="sxs-lookup"><span data-stu-id="2eab0-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
 <span data-ttu-id="2eab0-116">`New` 关键字可用于以下上下文中：</span><span class="sxs-lookup"><span data-stu-id="2eab0-116">The `New` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="2eab0-117">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="2eab0-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="2eab0-118">Of</span><span class="sxs-lookup"><span data-stu-id="2eab0-118">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [<span data-ttu-id="2eab0-119">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="2eab0-119">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="2eab0-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2eab0-120">See Also</span></span>  
 <xref:System.OutOfMemoryException>  
 [<span data-ttu-id="2eab0-121">关键字</span><span class="sxs-lookup"><span data-stu-id="2eab0-121">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="2eab0-122">类型列表</span><span class="sxs-lookup"><span data-stu-id="2eab0-122">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="2eab0-123">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="2eab0-123">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="2eab0-124">对象生存期：如何创建和销毁对象</span><span class="sxs-lookup"><span data-stu-id="2eab0-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
