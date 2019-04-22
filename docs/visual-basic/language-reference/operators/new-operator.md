---
title: New 运算符 (Visual Basic)
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
ms.openlocfilehash: 630b0c48def77449f426b287a26f95af7cfb930e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837686"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="354ce-102">New 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="354ce-102">New Operator (Visual Basic)</span></span>
<span data-ttu-id="354ce-103">引入了`New`子句，以创建新的对象实例，指定类型参数的构造函数约束或标识`Sub`作为类构造函数的过程。</span><span class="sxs-lookup"><span data-stu-id="354ce-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="354ce-104">备注</span><span class="sxs-lookup"><span data-stu-id="354ce-104">Remarks</span></span>  
 <span data-ttu-id="354ce-105">声明或赋值语句中`New`子句必须指定将从其创建实例定义的类。</span><span class="sxs-lookup"><span data-stu-id="354ce-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="354ce-106">这意味着类必须公开一个或多个构造函数的调用代码可以访问。</span><span class="sxs-lookup"><span data-stu-id="354ce-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>  
  
 <span data-ttu-id="354ce-107">可以使用`New`声明语句或赋值语句中的子句。</span><span class="sxs-lookup"><span data-stu-id="354ce-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="354ce-108">该语句在运行时将调用相应的构造函数的指定的类，并传入具有提供的所有参数。</span><span class="sxs-lookup"><span data-stu-id="354ce-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="354ce-109">下面的示例演示这通过创建的实例`Customer`类具有两个构造函数，一个不带参数，一个采用字符串参数。</span><span class="sxs-lookup"><span data-stu-id="354ce-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter.</span></span>  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 <span data-ttu-id="354ce-110">由于数组是类，`New`可以创建一个新数组实例，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="354ce-110">Since arrays are classes, `New` can create a new array instance, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 <span data-ttu-id="354ce-111">公共语言运行时 (CLR) 会引发<xref:System.OutOfMemoryException>错误是否存在内存不足，无法创建新实例。</span><span class="sxs-lookup"><span data-stu-id="354ce-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="354ce-112">`New`关键字还用于在类型形参列表中指定所提供的类型必须公开一个可访问的无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="354ce-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="354ce-113">有关类型参数和约束的详细信息，请参阅[类型列表](../../../visual-basic/language-reference/statements/type-list.md)。</span><span class="sxs-lookup"><span data-stu-id="354ce-113">For more information about type parameters and constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
 <span data-ttu-id="354ce-114">若要创建一个类的构造函数过程，请设置的名称`Sub`过程`New`关键字。</span><span class="sxs-lookup"><span data-stu-id="354ce-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="354ce-115">有关详细信息，请参阅[对象生存期：如何创建和销毁对象](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)。</span><span class="sxs-lookup"><span data-stu-id="354ce-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
 <span data-ttu-id="354ce-116">`New` 关键字可用于以下上下文中：</span><span class="sxs-lookup"><span data-stu-id="354ce-116">The `New` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="354ce-117">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="354ce-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="354ce-118">Of</span><span class="sxs-lookup"><span data-stu-id="354ce-118">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [<span data-ttu-id="354ce-119">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="354ce-119">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="354ce-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="354ce-120">See also</span></span>

- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="354ce-121">关键字</span><span class="sxs-lookup"><span data-stu-id="354ce-121">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="354ce-122">类型列表</span><span class="sxs-lookup"><span data-stu-id="354ce-122">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="354ce-123">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="354ce-123">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="354ce-124">对象生存期：如何创建和销毁对象</span><span class="sxs-lookup"><span data-stu-id="354ce-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
