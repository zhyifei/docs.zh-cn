---
title: "类型提升 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declared elements, scope
- visibility, declared elements
- Partial keyword, unexpected results with type promotion
- scope, declared elements
- scope, Visual Basic
- type promotion
- declared elements, visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 383f4b1d29e9bbf81eee44bf78762a80aea9eb36
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="type-promotion-visual-basic"></a><span data-ttu-id="c6269-102">类型提升 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6269-102">Type Promotion (Visual Basic)</span></span>
<span data-ttu-id="c6269-103">当您声明一个模块中的编程元素时[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]将提升其作用域限制为包含该模块的命名空间。</span><span class="sxs-lookup"><span data-stu-id="c6269-103">When you declare a programming element in a module, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] promotes its scope to the namespace containing the module.</span></span> <span data-ttu-id="c6269-104">这称为*类型提升*。</span><span class="sxs-lookup"><span data-stu-id="c6269-104">This is known as *type promotion*.</span></span>  
  
 <span data-ttu-id="c6269-105">下面的示例演示一个模块的主干定义和该模块的两个成员。</span><span class="sxs-lookup"><span data-stu-id="c6269-105">The following example shows a skeleton definition of a module and two members of that module.</span></span>  
  
 <span data-ttu-id="c6269-106">[!code-vb[VbVbalrDeclaredElements #&1;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c6269-106">[!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]</span></span>  
  
 <span data-ttu-id="c6269-107">在`projModule`、 编程在模块级别声明的元素将被提升到`projNamespace`。</span><span class="sxs-lookup"><span data-stu-id="c6269-107">Within `projModule`, programming elements declared at module level are promoted to `projNamespace`.</span></span> <span data-ttu-id="c6269-108">在前面的示例中，`basicEnum`和`innerClass`进行升级，但`numberSub`无效，因为它不在模块级别声明。</span><span class="sxs-lookup"><span data-stu-id="c6269-108">In the preceding example, `basicEnum` and `innerClass` are promoted, but `numberSub` is not, because it is not declared at module level.</span></span>  
  
## <a name="effect-of-type-promotion"></a><span data-ttu-id="c6269-109">类型提升的结果</span><span class="sxs-lookup"><span data-stu-id="c6269-109">Effect of Type Promotion</span></span>  
 <span data-ttu-id="c6269-110">类型提升的结果是一个限定字符串不需要包括该模块名称。</span><span class="sxs-lookup"><span data-stu-id="c6269-110">The effect of type promotion is that a qualification string does not need to include the module name.</span></span> <span data-ttu-id="c6269-111">下面的示例调用两个过程在前面的示例。</span><span class="sxs-lookup"><span data-stu-id="c6269-111">The following example makes two calls to the procedure in the preceding example.</span></span>  
  
 <span data-ttu-id="c6269-112">[!code-vb[VbVbalrDeclaredElements #&2;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c6269-112">[!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]</span></span>  
  
 <span data-ttu-id="c6269-113">在前面的示例中，第一次调用使用完全限定字符串。</span><span class="sxs-lookup"><span data-stu-id="c6269-113">In the preceding example, the first call uses complete qualification strings.</span></span> <span data-ttu-id="c6269-114">但是，这是不必要由于类型提升。</span><span class="sxs-lookup"><span data-stu-id="c6269-114">However, this is not necessary because of type promotion.</span></span> <span data-ttu-id="c6269-115">第二个调用也访问该模块的成员而不包括`projModule`限定字符串中。</span><span class="sxs-lookup"><span data-stu-id="c6269-115">The second call also accesses the module's members without including `projModule` in the qualification strings.</span></span>  
  
## <a name="defeat-of-type-promotion"></a><span data-ttu-id="c6269-116">类型提升的失效</span><span class="sxs-lookup"><span data-stu-id="c6269-116">Defeat of Type Promotion</span></span>  
 <span data-ttu-id="c6269-117">如果命名空间已具有相同的名称作为模块成员的成员，类型提升则会对该模块成员失效。</span><span class="sxs-lookup"><span data-stu-id="c6269-117">If the namespace already has a member with the same name as a module member, type promotion is defeated for that module member.</span></span> <span data-ttu-id="c6269-118">下面的示例演示了框架的枚举和同一命名空间中的模块定义。</span><span class="sxs-lookup"><span data-stu-id="c6269-118">The following example shows a skeleton definition of an enumeration and a module within the same namespace.</span></span>  
  
 <span data-ttu-id="c6269-119">[!code-vb[VbVbalrDeclaredElements #&3;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="c6269-119">[!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]</span></span>  
  
 <span data-ttu-id="c6269-120">在前面的示例中，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]无法提升类`abc`到`thisNameSpace`原因是已经存在具有相同的名称在命名空间级别的枚举。</span><span class="sxs-lookup"><span data-stu-id="c6269-120">In the preceding example, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot promote class `abc` to `thisNameSpace` because there is already an enumeration with the same name at namespace level.</span></span> <span data-ttu-id="c6269-121">访问`abcSub`，必须使用完全限定字符串`thisNamespace.thisModule.abc.abcSub`。</span><span class="sxs-lookup"><span data-stu-id="c6269-121">To access `abcSub`, you must use the full qualification string `thisNamespace.thisModule.abc.abcSub`.</span></span> <span data-ttu-id="c6269-122">但是，类`xyz`仍会提升，并且可以访问`xyzSub`较短的限定字符串`thisNamespace.xyz.xyzSub`。</span><span class="sxs-lookup"><span data-stu-id="c6269-122">However, class `xyz` is still promoted, and you can access `xyzSub` with the shorter qualification string `thisNamespace.xyz.xyzSub`.</span></span>  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a><span data-ttu-id="c6269-123">分部类型的类型提升的失效</span><span class="sxs-lookup"><span data-stu-id="c6269-123">Defeat of Type Promotion for Partial Types</span></span>  
 <span data-ttu-id="c6269-124">如果某个类或模块内的结构使用[部分](../../../../visual-basic/language-reference/modifiers/partial.md)关键字，类型提升自动失效该类或结构中，无论是命名空间包含具有相同名称的成员。</span><span class="sxs-lookup"><span data-stu-id="c6269-124">If a class or structure inside a module uses the [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) keyword, type promotion is automatically defeated for that class or structure, whether or not the namespace has a member with the same name.</span></span> <span data-ttu-id="c6269-125">该模块中的其他元素都仍可进行类型提升。</span><span class="sxs-lookup"><span data-stu-id="c6269-125">Other elements in the module are still eligible for type promotion.</span></span>  
  
 <span data-ttu-id="c6269-126">**后果。**</span><span class="sxs-lookup"><span data-stu-id="c6269-126">**Consequences.**</span></span> <span data-ttu-id="c6269-127">部分定义的类型提升的失效可能导致意外的结果和甚至编译器错误。</span><span class="sxs-lookup"><span data-stu-id="c6269-127">Defeat of type promotion of a partial definition can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="c6269-128">下面的示例演示一个类，其中之一是模块内的主干分部定义。</span><span class="sxs-lookup"><span data-stu-id="c6269-128">The following example shows skeleton partial definitions of a class, one of which is inside a module.</span></span>  
  
 <span data-ttu-id="c6269-129">[!code-vb[VbVbalrDeclaredElements #&4;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="c6269-129">[!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]</span></span>  
  
 <span data-ttu-id="c6269-130">在前面的示例中，开发人员可能期望编译器要合并的两个部分定义`sampleClass`。</span><span class="sxs-lookup"><span data-stu-id="c6269-130">In the preceding example, the developer might expect the compiler to merge the two partial definitions of `sampleClass`.</span></span> <span data-ttu-id="c6269-131">但是，编译器不会考虑的促销内分部定义`sampleModule`。</span><span class="sxs-lookup"><span data-stu-id="c6269-131">However, the compiler does not consider promotion for the partial definition inside `sampleModule`.</span></span> <span data-ttu-id="c6269-132">结果是，它尝试编译两个独立但截然不同的类，名为`sampleClass`但具有不同限定路径。</span><span class="sxs-lookup"><span data-stu-id="c6269-132">As a result, it attempts to compile two separate and distinct classes, both named `sampleClass` but with different qualification paths.</span></span>  
  
 <span data-ttu-id="c6269-133">仅当其完全限定的路径相同时，编译器才将合并分部定义。</span><span class="sxs-lookup"><span data-stu-id="c6269-133">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="c6269-134">建议</span><span class="sxs-lookup"><span data-stu-id="c6269-134">Recommendations</span></span>  
 <span data-ttu-id="c6269-135">下面的建议提供良好编程习惯。</span><span class="sxs-lookup"><span data-stu-id="c6269-135">The following recommendations represent good programming practice.</span></span>  
  
-   <span data-ttu-id="c6269-136">**唯一的名称。**</span><span class="sxs-lookup"><span data-stu-id="c6269-136">**Unique Names.**</span></span> <span data-ttu-id="c6269-137">如果必须对编程元素的命名的完全控制，并总是最好是不同的场合使用唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="c6269-137">When you have full control over the naming of programming elements, it is always a good idea to use unique names everywhere.</span></span> <span data-ttu-id="c6269-138">相同的名称需要额外的限定，并且会导致代码更难读懂。</span><span class="sxs-lookup"><span data-stu-id="c6269-138">Identical names require extra qualification and can make your code harder to read.</span></span> <span data-ttu-id="c6269-139">它们也可能会带来细微错误和意外的结果。</span><span class="sxs-lookup"><span data-stu-id="c6269-139">They can also lead to subtle errors and unexpected results.</span></span>  
  
-   <span data-ttu-id="c6269-140">**完全限定。**</span><span class="sxs-lookup"><span data-stu-id="c6269-140">**Full Qualification.**</span></span> <span data-ttu-id="c6269-141">当您正在使用模块和相同的命名空间中的其他元素时，最安全的方法是始终使用完全限定的所有编程元素。</span><span class="sxs-lookup"><span data-stu-id="c6269-141">When you are working with modules and other elements in the same namespace, the safest approach is to always use full qualification for all programming elements.</span></span> <span data-ttu-id="c6269-142">如果使某个模块成员的类型提升无效，并且不完全限定该成员，您可能无意中访问不同的编程元素。</span><span class="sxs-lookup"><span data-stu-id="c6269-142">If type promotion is defeated for a module member and you do not fully qualify that member, you could inadvertently access a different programming element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6269-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6269-143">See Also</span></span>  
 <span data-ttu-id="c6269-144">[Module 语句](../../../../visual-basic/language-reference/statements/module-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c6269-144">[Module Statement](../../../../visual-basic/language-reference/statements/module-statement.md) </span></span>  
<span data-ttu-id="c6269-145"> [Namespace 语句](../../../../visual-basic/language-reference/statements/namespace-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c6269-145"> [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md) </span></span>  
<span data-ttu-id="c6269-146"> [部分](../../../../visual-basic/language-reference/modifiers/partial.md) </span><span class="sxs-lookup"><span data-stu-id="c6269-146"> [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) </span></span>  
<span data-ttu-id="c6269-147"> [在 Visual Basic 中的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md) </span><span class="sxs-lookup"><span data-stu-id="c6269-147"> [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md) </span></span>  
<span data-ttu-id="c6269-148"> [如何︰ 控制变量的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md) </span><span class="sxs-lookup"><span data-stu-id="c6269-148"> [How to: Control the Scope of a Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md) </span></span>  
<span data-ttu-id="c6269-149"> [对已声明元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span><span class="sxs-lookup"><span data-stu-id="c6269-149"> [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span></span>
