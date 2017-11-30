---
title: "类型提升 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f3a55c023afe7afe96f862f0b3cbbdb03a15b902
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="type-promotion-visual-basic"></a><span data-ttu-id="fb28a-102">类型提升 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb28a-102">Type Promotion (Visual Basic)</span></span>
<span data-ttu-id="fb28a-103">当你声明一个模块中的编程元素时[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]提升其作用域限制为包含该模块的命名空间。</span><span class="sxs-lookup"><span data-stu-id="fb28a-103">When you declare a programming element in a module, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] promotes its scope to the namespace containing the module.</span></span> <span data-ttu-id="fb28a-104">这称为*类型提升*。</span><span class="sxs-lookup"><span data-stu-id="fb28a-104">This is known as *type promotion*.</span></span>  
  
 <span data-ttu-id="fb28a-105">下面的示例演示了模块的主干定义而且该模块的两个成员。</span><span class="sxs-lookup"><span data-stu-id="fb28a-105">The following example shows a skeleton definition of a module and two members of that module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 <span data-ttu-id="fb28a-106">在`projModule`、 编程在模块级别声明的元素将被提升到`projNamespace`。</span><span class="sxs-lookup"><span data-stu-id="fb28a-106">Within `projModule`, programming elements declared at module level are promoted to `projNamespace`.</span></span> <span data-ttu-id="fb28a-107">在前面的示例中，`basicEnum`和`innerClass`提升，但`numberSub`无效，因为不能在模块级别声明。</span><span class="sxs-lookup"><span data-stu-id="fb28a-107">In the preceding example, `basicEnum` and `innerClass` are promoted, but `numberSub` is not, because it is not declared at module level.</span></span>  
  
## <a name="effect-of-type-promotion"></a><span data-ttu-id="fb28a-108">类型提升的结果</span><span class="sxs-lookup"><span data-stu-id="fb28a-108">Effect of Type Promotion</span></span>  
 <span data-ttu-id="fb28a-109">类型提升的效果是限定字符串不需要包含模块名称。</span><span class="sxs-lookup"><span data-stu-id="fb28a-109">The effect of type promotion is that a qualification string does not need to include the module name.</span></span> <span data-ttu-id="fb28a-110">下面的示例调用两个过程在前面的示例。</span><span class="sxs-lookup"><span data-stu-id="fb28a-110">The following example makes two calls to the procedure in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 <span data-ttu-id="fb28a-111">在前面的示例中，第一次调用使用完全限定字符串。</span><span class="sxs-lookup"><span data-stu-id="fb28a-111">In the preceding example, the first call uses complete qualification strings.</span></span> <span data-ttu-id="fb28a-112">但是，这是不必要由于类型提升。</span><span class="sxs-lookup"><span data-stu-id="fb28a-112">However, this is not necessary because of type promotion.</span></span> <span data-ttu-id="fb28a-113">第二个调用也访问模块成员而不包括`projModule`限定字符串中。</span><span class="sxs-lookup"><span data-stu-id="fb28a-113">The second call also accesses the module's members without including `projModule` in the qualification strings.</span></span>  
  
## <a name="defeat-of-type-promotion"></a><span data-ttu-id="fb28a-114">类型提升失效</span><span class="sxs-lookup"><span data-stu-id="fb28a-114">Defeat of Type Promotion</span></span>  
 <span data-ttu-id="fb28a-115">如果命名空间已具有相同的名称作为模块成员的成员，使该模块成员的类型提升无效。</span><span class="sxs-lookup"><span data-stu-id="fb28a-115">If the namespace already has a member with the same name as a module member, type promotion is defeated for that module member.</span></span> <span data-ttu-id="fb28a-116">下面的示例演示一个枚举和相同的命名空间内的模块的主干定义。</span><span class="sxs-lookup"><span data-stu-id="fb28a-116">The following example shows a skeleton definition of an enumeration and a module within the same namespace.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 <span data-ttu-id="fb28a-117">在前面的示例中，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]无法提升类`abc`到`thisNameSpace`原因是已经存在具有相同名称在命名空间级别的枚举。</span><span class="sxs-lookup"><span data-stu-id="fb28a-117">In the preceding example, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot promote class `abc` to `thisNameSpace` because there is already an enumeration with the same name at namespace level.</span></span> <span data-ttu-id="fb28a-118">访问`abcSub`，必须使用完全限定字符串`thisNamespace.thisModule.abc.abcSub`。</span><span class="sxs-lookup"><span data-stu-id="fb28a-118">To access `abcSub`, you must use the full qualification string `thisNamespace.thisModule.abc.abcSub`.</span></span> <span data-ttu-id="fb28a-119">但是，类`xyz`仍会提升，并且可以访问`xyzSub`与使用较短的限定字符串`thisNamespace.xyz.xyzSub`。</span><span class="sxs-lookup"><span data-stu-id="fb28a-119">However, class `xyz` is still promoted, and you can access `xyzSub` with the shorter qualification string `thisNamespace.xyz.xyzSub`.</span></span>  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a><span data-ttu-id="fb28a-120">分部类型的类型提升的失效</span><span class="sxs-lookup"><span data-stu-id="fb28a-120">Defeat of Type Promotion for Partial Types</span></span>  
 <span data-ttu-id="fb28a-121">如果类或结构在模块内的使用[部分](../../../../visual-basic/language-reference/modifiers/partial.md)关键字，类型提升会自动失效该类或结构，无论该命名空间具有具有相同名称的成员。</span><span class="sxs-lookup"><span data-stu-id="fb28a-121">If a class or structure inside a module uses the [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) keyword, type promotion is automatically defeated for that class or structure, whether or not the namespace has a member with the same name.</span></span> <span data-ttu-id="fb28a-122">该模块中的其他元素都仍可进行类型提升。</span><span class="sxs-lookup"><span data-stu-id="fb28a-122">Other elements in the module are still eligible for type promotion.</span></span>  
  
 <span data-ttu-id="fb28a-123">**后果。**</span><span class="sxs-lookup"><span data-stu-id="fb28a-123">**Consequences.**</span></span> <span data-ttu-id="fb28a-124">意外的结果，甚至编译器错误，则可能会导致的部分定义的类型提升的失效。</span><span class="sxs-lookup"><span data-stu-id="fb28a-124">Defeat of type promotion of a partial definition can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="fb28a-125">下面的示例演示其中之一是在模块内的类的主干分部定义。</span><span class="sxs-lookup"><span data-stu-id="fb28a-125">The following example shows skeleton partial definitions of a class, one of which is inside a module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 <span data-ttu-id="fb28a-126">在前面的示例中，开发人员可能希望合并的两个分部定义编译器`sampleClass`。</span><span class="sxs-lookup"><span data-stu-id="fb28a-126">In the preceding example, the developer might expect the compiler to merge the two partial definitions of `sampleClass`.</span></span> <span data-ttu-id="fb28a-127">但是，编译器不会考虑的分部定义内的升级`sampleModule`。</span><span class="sxs-lookup"><span data-stu-id="fb28a-127">However, the compiler does not consider promotion for the partial definition inside `sampleModule`.</span></span> <span data-ttu-id="fb28a-128">因此，它将尝试编译两个单独的且不同类、 命名`sampleClass`但具有不同限定路径。</span><span class="sxs-lookup"><span data-stu-id="fb28a-128">As a result, it attempts to compile two separate and distinct classes, both named `sampleClass` but with different qualification paths.</span></span>  
  
 <span data-ttu-id="fb28a-129">仅当其完全限定的路径相同时，编译器才将合并分部定义。</span><span class="sxs-lookup"><span data-stu-id="fb28a-129">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="fb28a-130">建议</span><span class="sxs-lookup"><span data-stu-id="fb28a-130">Recommendations</span></span>  
 <span data-ttu-id="fb28a-131">下面的建议提供良好编程习惯。</span><span class="sxs-lookup"><span data-stu-id="fb28a-131">The following recommendations represent good programming practice.</span></span>  
  
-   <span data-ttu-id="fb28a-132">**唯一的名称。**</span><span class="sxs-lookup"><span data-stu-id="fb28a-132">**Unique Names.**</span></span> <span data-ttu-id="fb28a-133">如果必须对编程元素的命名的完全控制，并总是最好无处不在使用唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="fb28a-133">When you have full control over the naming of programming elements, it is always a good idea to use unique names everywhere.</span></span> <span data-ttu-id="fb28a-134">相同的名称需要额外的限定，并且可以使代码难以阅读。</span><span class="sxs-lookup"><span data-stu-id="fb28a-134">Identical names require extra qualification and can make your code harder to read.</span></span> <span data-ttu-id="fb28a-135">此外，它们还可能导致细微的错误和意外的结果。</span><span class="sxs-lookup"><span data-stu-id="fb28a-135">They can also lead to subtle errors and unexpected results.</span></span>  
  
-   <span data-ttu-id="fb28a-136">**完全限定。**</span><span class="sxs-lookup"><span data-stu-id="fb28a-136">**Full Qualification.**</span></span> <span data-ttu-id="fb28a-137">当你使用模块和相同的命名空间中的其他元素时，最安全的方法是始终对所有的编程元素中使用完全限定。</span><span class="sxs-lookup"><span data-stu-id="fb28a-137">When you are working with modules and other elements in the same namespace, the safest approach is to always use full qualification for all programming elements.</span></span> <span data-ttu-id="fb28a-138">如果使某个模块成员的类型提升并不完全限定该成员，你无意中无法访问不同的编程元素。</span><span class="sxs-lookup"><span data-stu-id="fb28a-138">If type promotion is defeated for a module member and you do not fully qualify that member, you could inadvertently access a different programming element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb28a-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb28a-139">See Also</span></span>  
 [<span data-ttu-id="fb28a-140">Module 语句</span><span class="sxs-lookup"><span data-stu-id="fb28a-140">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [<span data-ttu-id="fb28a-141">Namespace 语句</span><span class="sxs-lookup"><span data-stu-id="fb28a-141">Namespace Statement</span></span>](../../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="fb28a-142">Partial</span><span class="sxs-lookup"><span data-stu-id="fb28a-142">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [<span data-ttu-id="fb28a-143">在 Visual Basic 中的作用域</span><span class="sxs-lookup"><span data-stu-id="fb28a-143">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [<span data-ttu-id="fb28a-144">如何：控制变量的范围</span><span class="sxs-lookup"><span data-stu-id="fb28a-144">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)  
 [<span data-ttu-id="fb28a-145">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="fb28a-145">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
