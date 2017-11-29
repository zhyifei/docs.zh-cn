---
title: "分部方法 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8ebedd6f8173e3c349240d24ddaf16e4841f67a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="partial-methods-visual-basic"></a><span data-ttu-id="571d1-102">分部方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="571d1-102">Partial Methods (Visual Basic)</span></span>
<span data-ttu-id="571d1-103">分部方法允许开发人员将自定义逻辑插入到代码。</span><span class="sxs-lookup"><span data-stu-id="571d1-103">Partial methods enable developers to insert custom logic into code.</span></span> <span data-ttu-id="571d1-104">通常情况下，代码是类的设计器生成的一部分。</span><span class="sxs-lookup"><span data-stu-id="571d1-104">Typically, the code is part of a designer-generated class.</span></span> <span data-ttu-id="571d1-105">分部方法定义中创建的代码生成器中，分部类和它们通常用于提供的内容已更改的通知。</span><span class="sxs-lookup"><span data-stu-id="571d1-105">Partial methods are defined in a partial class that is created by a code generator, and they are commonly used to provide notification that something has been changed.</span></span> <span data-ttu-id="571d1-106">它们使开发人员在更改的响应中指定自定义行为。</span><span class="sxs-lookup"><span data-stu-id="571d1-106">They enable the developer to specify custom behavior in response to the change.</span></span>  
  
 <span data-ttu-id="571d1-107">代码生成器的设计器定义仅方法签名和对方法的一个或多个调用。</span><span class="sxs-lookup"><span data-stu-id="571d1-107">The designer of the code generator defines only the method signature and one or more calls to the method.</span></span> <span data-ttu-id="571d1-108">如果他们想要自定义生成代码的行为，开发人员然后可以提供的方法的实现。</span><span class="sxs-lookup"><span data-stu-id="571d1-108">Developers can then provide implementations for the method if they want to customize the behavior of the generated code.</span></span> <span data-ttu-id="571d1-109">如果没有实现，则对方法的调用将删除由编译器，导致产生其他性能开销。</span><span class="sxs-lookup"><span data-stu-id="571d1-109">When no implementation is provided, calls to the method are removed by the compiler, resulting in no additional performance overhead.</span></span>  
  
## <a name="declaration"></a><span data-ttu-id="571d1-110">声明</span><span class="sxs-lookup"><span data-stu-id="571d1-110">Declaration</span></span>  
 <span data-ttu-id="571d1-111">生成的代码的分部方法的定义标记放置关键字`Partial`签名行的开头。</span><span class="sxs-lookup"><span data-stu-id="571d1-111">The generated code marks the definition of a partial method by placing the keyword `Partial` at the start of the signature line.</span></span>  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 <span data-ttu-id="571d1-112">定义必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="571d1-112">The definition must meet the following conditions:</span></span>  
  
-   <span data-ttu-id="571d1-113">该方法必须是`Sub`，而不`Function`。</span><span class="sxs-lookup"><span data-stu-id="571d1-113">The method must be a `Sub`, not a `Function`.</span></span>  
  
-   <span data-ttu-id="571d1-114">方法的主体必须保留为空。</span><span class="sxs-lookup"><span data-stu-id="571d1-114">The body of the method must be left empty.</span></span>  
  
-   <span data-ttu-id="571d1-115">访问修饰符必须`Private`。</span><span class="sxs-lookup"><span data-stu-id="571d1-115">The access modifier must be `Private`.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="571d1-116">实现</span><span class="sxs-lookup"><span data-stu-id="571d1-116">Implementation</span></span>  
 <span data-ttu-id="571d1-117">实现主要由于填写分部方法的正文。</span><span class="sxs-lookup"><span data-stu-id="571d1-117">The implementation consists primarily of filling in the body of the partial method.</span></span> <span data-ttu-id="571d1-118">实现通常是在定义中，单独的分部类中，并且由开发人员希望将扩展到生成的代码编写。</span><span class="sxs-lookup"><span data-stu-id="571d1-118">The implementation is typically in a separate partial class from the definition, and is written by a developer who wants to extend the generated code.</span></span>  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 <span data-ttu-id="571d1-119">前面的示例重复中声明的签名完全匹配，但可以变体。</span><span class="sxs-lookup"><span data-stu-id="571d1-119">The previous example duplicates the signature in the declaration exactly, but variations are possible.</span></span> <span data-ttu-id="571d1-120">具体而言，其他可以添加修饰符，如`Overloads`或`Overrides`。</span><span class="sxs-lookup"><span data-stu-id="571d1-120">In particular, other modifiers can be added, such as `Overloads` or `Overrides`.</span></span> <span data-ttu-id="571d1-121">只有一个`Overrides`允许使用修饰符。</span><span class="sxs-lookup"><span data-stu-id="571d1-121">Only one `Overrides` modifier is permitted.</span></span> <span data-ttu-id="571d1-122">有关方法修饰符的详细信息，请参阅[Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="571d1-122">For more information about method modifiers, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="use"></a><span data-ttu-id="571d1-123">使用</span><span class="sxs-lookup"><span data-stu-id="571d1-123">Use</span></span>  
 <span data-ttu-id="571d1-124">你调用分部方法，如将调用任何其他`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="571d1-124">You call a partial method as you would call any other `Sub` procedure.</span></span> <span data-ttu-id="571d1-125">如果尚未实施方法，计算自变量并在执行方法的正文。</span><span class="sxs-lookup"><span data-stu-id="571d1-125">If the method has been implemented, the arguments are evaluated and the body of the method is executed.</span></span> <span data-ttu-id="571d1-126">但请记住，实现分部方法是可选的。</span><span class="sxs-lookup"><span data-stu-id="571d1-126">However, remember that implementing a partial method is optional.</span></span> <span data-ttu-id="571d1-127">如果未实现方法，它调用具有不起作用，并且无法计算的表达式作为自变量传递给方法。</span><span class="sxs-lookup"><span data-stu-id="571d1-127">If the method is not implemented, a call to it has no effect, and expressions passed as arguments to the method are not evaluated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="571d1-128">示例</span><span class="sxs-lookup"><span data-stu-id="571d1-128">Example</span></span>  
 <span data-ttu-id="571d1-129">在文件中名，定义`Product`具有类`Quantity`属性。</span><span class="sxs-lookup"><span data-stu-id="571d1-129">In a file named Product.Designer.vb, define a `Product` class that has a `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#4](./codesnippet/VisualBasic/partial-methods_1.vb)]  
  
 <span data-ttu-id="571d1-130">在文件中名，提供一个实现`QuantityChanged`。</span><span class="sxs-lookup"><span data-stu-id="571d1-130">In a file named Product.vb, provide an implementation for `QuantityChanged`.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#5](./codesnippet/VisualBasic/partial-methods_2.vb)]  
  
 <span data-ttu-id="571d1-131">最后，在 Main 方法中一个项目中，声明`Product`实例并提供的初始值其`Quantity`属性。</span><span class="sxs-lookup"><span data-stu-id="571d1-131">Finally, in the Main method of a project, declare a `Product` instance and provide an initial value for its `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#6](./codesnippet/VisualBasic/partial-methods_3.vb)]  
  
 <span data-ttu-id="571d1-132">应出现一个消息框，显示此消息：</span><span class="sxs-lookup"><span data-stu-id="571d1-132">A message box should appear that displays this message:</span></span>  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a><span data-ttu-id="571d1-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="571d1-133">See Also</span></span>  
 [<span data-ttu-id="571d1-134">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="571d1-134">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="571d1-135">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="571d1-135">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="571d1-136">可选参数</span><span class="sxs-lookup"><span data-stu-id="571d1-136">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="571d1-137">Partial</span><span class="sxs-lookup"><span data-stu-id="571d1-137">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [<span data-ttu-id="571d1-138">LINQ to SQL 中的代码生成</span><span class="sxs-lookup"><span data-stu-id="571d1-138">Code Generation in LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb399400)  
 [<span data-ttu-id="571d1-139">通过使用分部方法添加业务逻辑</span><span class="sxs-lookup"><span data-stu-id="571d1-139">Adding Business Logic By Using Partial Methods</span></span>](https://msdn.microsoft.com/library/bb546176)
