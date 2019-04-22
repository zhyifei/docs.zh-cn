---
title: 分部方法 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.PartialMethod
- PartialMethod
helpviewer_keywords:
- custom logic into code [Visual Basic]
- partial methods [Visual Basic]
- partial [Visual Basic], methods [Visual Basic]
- methods [Visual Basic], partial methods
- inserting custom logic into code
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
ms.openlocfilehash: 765a667f18340c53909c3ff1e9fcc5f2ffc0f9bc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837463"
---
# <a name="partial-methods-visual-basic"></a><span data-ttu-id="266b5-102">分部方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="266b5-102">Partial Methods (Visual Basic)</span></span>
<span data-ttu-id="266b5-103">分部方法使开发人员能够将自定义逻辑插入到代码。</span><span class="sxs-lookup"><span data-stu-id="266b5-103">Partial methods enable developers to insert custom logic into code.</span></span> <span data-ttu-id="266b5-104">通常情况下，代码是类的一个设计器生成的一部分。</span><span class="sxs-lookup"><span data-stu-id="266b5-104">Typically, the code is part of a designer-generated class.</span></span> <span data-ttu-id="266b5-105">分部方法中创建的代码生成器的分部类定义和它们通常用于提供的内容已更改的通知。</span><span class="sxs-lookup"><span data-stu-id="266b5-105">Partial methods are defined in a partial class that is created by a code generator, and they are commonly used to provide notification that something has been changed.</span></span> <span data-ttu-id="266b5-106">它们使开发人员指定自定义行为响应更改。</span><span class="sxs-lookup"><span data-stu-id="266b5-106">They enable the developer to specify custom behavior in response to the change.</span></span>  
  
 <span data-ttu-id="266b5-107">代码生成器的设计器定义仅在方法签名和对方法的一个或多个调用。</span><span class="sxs-lookup"><span data-stu-id="266b5-107">The designer of the code generator defines only the method signature and one or more calls to the method.</span></span> <span data-ttu-id="266b5-108">如果用户想要自定义生成的代码的行为，开发人员然后可以提供方法的实现。</span><span class="sxs-lookup"><span data-stu-id="266b5-108">Developers can then provide implementations for the method if they want to customize the behavior of the generated code.</span></span> <span data-ttu-id="266b5-109">时未不提供任何实现，对方法的调用将删除由编译器，从而导致任何额外的性能开销。</span><span class="sxs-lookup"><span data-stu-id="266b5-109">When no implementation is provided, calls to the method are removed by the compiler, resulting in no additional performance overhead.</span></span>  
  
## <a name="declaration"></a><span data-ttu-id="266b5-110">声明</span><span class="sxs-lookup"><span data-stu-id="266b5-110">Declaration</span></span>  
 <span data-ttu-id="266b5-111">生成的代码的分部方法定义标记上来将关键字`Partial`签名行的开头。</span><span class="sxs-lookup"><span data-stu-id="266b5-111">The generated code marks the definition of a partial method by placing the keyword `Partial` at the start of the signature line.</span></span>  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 <span data-ttu-id="266b5-112">定义必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="266b5-112">The definition must meet the following conditions:</span></span>  
  
-   <span data-ttu-id="266b5-113">该方法必须是`Sub`，而不`Function`。</span><span class="sxs-lookup"><span data-stu-id="266b5-113">The method must be a `Sub`, not a `Function`.</span></span>  
  
-   <span data-ttu-id="266b5-114">方法的主体必须保留为空。</span><span class="sxs-lookup"><span data-stu-id="266b5-114">The body of the method must be left empty.</span></span>  
  
-   <span data-ttu-id="266b5-115">访问修饰符必须`Private`。</span><span class="sxs-lookup"><span data-stu-id="266b5-115">The access modifier must be `Private`.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="266b5-116">实现</span><span class="sxs-lookup"><span data-stu-id="266b5-116">Implementation</span></span>  
 <span data-ttu-id="266b5-117">实现主要包含分部方法的正文中填充。</span><span class="sxs-lookup"><span data-stu-id="266b5-117">The implementation consists primarily of filling in the body of the partial method.</span></span> <span data-ttu-id="266b5-118">实现通常是在单独的分部类定义中，并由一名开发人员想要扩展生成的代码编写。</span><span class="sxs-lookup"><span data-stu-id="266b5-118">The implementation is typically in a separate partial class from the definition, and is written by a developer who wants to extend the generated code.</span></span>  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 <span data-ttu-id="266b5-119">前面的示例重复在声明中的签名完全正确，但可能变体。</span><span class="sxs-lookup"><span data-stu-id="266b5-119">The previous example duplicates the signature in the declaration exactly, but variations are possible.</span></span> <span data-ttu-id="266b5-120">具体而言，其他可以添加修饰符，如`Overloads`或`Overrides`。</span><span class="sxs-lookup"><span data-stu-id="266b5-120">In particular, other modifiers can be added, such as `Overloads` or `Overrides`.</span></span> <span data-ttu-id="266b5-121">只有一个`Overrides`允许使用修饰符。</span><span class="sxs-lookup"><span data-stu-id="266b5-121">Only one `Overrides` modifier is permitted.</span></span> <span data-ttu-id="266b5-122">有关方法的修饰符的详细信息，请参阅[Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="266b5-122">For more information about method modifiers, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="use"></a><span data-ttu-id="266b5-123">使用</span><span class="sxs-lookup"><span data-stu-id="266b5-123">Use</span></span>  
 <span data-ttu-id="266b5-124">调用任何其他方式调用的分部方法`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="266b5-124">You call a partial method as you would call any other `Sub` procedure.</span></span> <span data-ttu-id="266b5-125">如果已实现方法，计算自变量和执行方法的主体。</span><span class="sxs-lookup"><span data-stu-id="266b5-125">If the method has been implemented, the arguments are evaluated and the body of the method is executed.</span></span> <span data-ttu-id="266b5-126">但请记住，实现分部方法是可选的。</span><span class="sxs-lookup"><span data-stu-id="266b5-126">However, remember that implementing a partial method is optional.</span></span> <span data-ttu-id="266b5-127">如果未实现方法，则调用不起任何作用，并且无法计算的表达式作为参数传递给该方法。</span><span class="sxs-lookup"><span data-stu-id="266b5-127">If the method is not implemented, a call to it has no effect, and expressions passed as arguments to the method are not evaluated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="266b5-128">示例</span><span class="sxs-lookup"><span data-stu-id="266b5-128">Example</span></span>  
 <span data-ttu-id="266b5-129">在文件中名，定义`Product`类具有`Quantity`属性。</span><span class="sxs-lookup"><span data-stu-id="266b5-129">In a file named Product.Designer.vb, define a `Product` class that has a `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#4)]  
  
 <span data-ttu-id="266b5-130">在文件中名，提供的实现`QuantityChanged`。</span><span class="sxs-lookup"><span data-stu-id="266b5-130">In a file named Product.vb, provide an implementation for `QuantityChanged`.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#5)]  
  
 <span data-ttu-id="266b5-131">最后，在项目的 Main 方法中，声明`Product`实例，并提供一个初始值及其`Quantity`属性。</span><span class="sxs-lookup"><span data-stu-id="266b5-131">Finally, in the Main method of a project, declare a `Product` instance and provide an initial value for its `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#6)]  
  
 <span data-ttu-id="266b5-132">应出现一个消息框将显示此消息：</span><span class="sxs-lookup"><span data-stu-id="266b5-132">A message box should appear that displays this message:</span></span>  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a><span data-ttu-id="266b5-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="266b5-133">See also</span></span>

- [<span data-ttu-id="266b5-134">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="266b5-134">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="266b5-135">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="266b5-135">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="266b5-136">可选参数</span><span class="sxs-lookup"><span data-stu-id="266b5-136">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="266b5-137">Partial</span><span class="sxs-lookup"><span data-stu-id="266b5-137">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)
- [<span data-ttu-id="266b5-138">LINQ to SQL 中的代码生成</span><span class="sxs-lookup"><span data-stu-id="266b5-138">Code Generation in LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="266b5-139">通过使用分部方法添加业务逻辑</span><span class="sxs-lookup"><span data-stu-id="266b5-139">Adding Business Logic By Using Partial Methods</span></span>](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
