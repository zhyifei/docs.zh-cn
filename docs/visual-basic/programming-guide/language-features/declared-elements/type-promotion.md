---
title: 类型提升 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
ms.openlocfilehash: f7ac6bfb944da8bd50e035ba97b2b513176dc661
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838867"
---
# <a name="type-promotion-visual-basic"></a><span data-ttu-id="ef87b-102">类型提升 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef87b-102">Type Promotion (Visual Basic)</span></span>
<span data-ttu-id="ef87b-103">声明模块中的编程元素时，Visual Basic 会将其范围到包含该模块的命名空间的提升。</span><span class="sxs-lookup"><span data-stu-id="ef87b-103">When you declare a programming element in a module, Visual Basic promotes its scope to the namespace containing the module.</span></span> <span data-ttu-id="ef87b-104">这称为*类型提升*。</span><span class="sxs-lookup"><span data-stu-id="ef87b-104">This is known as *type promotion*.</span></span>  
  
 <span data-ttu-id="ef87b-105">下面的示例演示一个模块的主干定义和该模块的两个成员。</span><span class="sxs-lookup"><span data-stu-id="ef87b-105">The following example shows a skeleton definition of a module and two members of that module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#1)]  
  
 <span data-ttu-id="ef87b-106">内`projModule`编程中，在模块级别声明的元素将被提升到`projNamespace`。</span><span class="sxs-lookup"><span data-stu-id="ef87b-106">Within `projModule`, programming elements declared at module level are promoted to `projNamespace`.</span></span> <span data-ttu-id="ef87b-107">在前面的示例中，`basicEnum`并`innerClass`进行升级，但`numberSub`无效，因为不能在模块级别声明。</span><span class="sxs-lookup"><span data-stu-id="ef87b-107">In the preceding example, `basicEnum` and `innerClass` are promoted, but `numberSub` is not, because it is not declared at module level.</span></span>  
  
## <a name="effect-of-type-promotion"></a><span data-ttu-id="ef87b-108">类型提升的结果</span><span class="sxs-lookup"><span data-stu-id="ef87b-108">Effect of Type Promotion</span></span>  
 <span data-ttu-id="ef87b-109">类型提升的效果是限定字符串不需要包含模块名称。</span><span class="sxs-lookup"><span data-stu-id="ef87b-109">The effect of type promotion is that a qualification string does not need to include the module name.</span></span> <span data-ttu-id="ef87b-110">下面的示例调用两个过程在前面的示例。</span><span class="sxs-lookup"><span data-stu-id="ef87b-110">The following example makes two calls to the procedure in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#2)]  
  
 <span data-ttu-id="ef87b-111">在前面的示例中，第一次调用使用完全限定字符串。</span><span class="sxs-lookup"><span data-stu-id="ef87b-111">In the preceding example, the first call uses complete qualification strings.</span></span> <span data-ttu-id="ef87b-112">但是，这是不必要因为类型提升。</span><span class="sxs-lookup"><span data-stu-id="ef87b-112">However, this is not necessary because of type promotion.</span></span> <span data-ttu-id="ef87b-113">第二个调用也访问该模块的成员而不包括`projModule`限定字符串中。</span><span class="sxs-lookup"><span data-stu-id="ef87b-113">The second call also accesses the module's members without including `projModule` in the qualification strings.</span></span>  
  
## <a name="defeat-of-type-promotion"></a><span data-ttu-id="ef87b-114">类型提升失效</span><span class="sxs-lookup"><span data-stu-id="ef87b-114">Defeat of Type Promotion</span></span>  
 <span data-ttu-id="ef87b-115">如果命名空间已有一个同名成员模块成员，类型提升则会为该模块成员失效。</span><span class="sxs-lookup"><span data-stu-id="ef87b-115">If the namespace already has a member with the same name as a module member, type promotion is defeated for that module member.</span></span> <span data-ttu-id="ef87b-116">下面的示例显示了枚举和相同的命名空间内的模块的主干定义。</span><span class="sxs-lookup"><span data-stu-id="ef87b-116">The following example shows a skeleton definition of an enumeration and a module within the same namespace.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#3)]  
  
 <span data-ttu-id="ef87b-117">在前面的示例中，Visual Basic 不能将类提升`abc`到`thisNameSpace`因为已存在具有相同的名称在命名空间级别的枚举。</span><span class="sxs-lookup"><span data-stu-id="ef87b-117">In the preceding example, Visual Basic cannot promote class `abc` to `thisNameSpace` because there is already an enumeration with the same name at namespace level.</span></span> <span data-ttu-id="ef87b-118">访问`abcSub`，必须使用完全限定字符串`thisNamespace.thisModule.abc.abcSub`。</span><span class="sxs-lookup"><span data-stu-id="ef87b-118">To access `abcSub`, you must use the full qualification string `thisNamespace.thisModule.abc.abcSub`.</span></span> <span data-ttu-id="ef87b-119">但是，类`xyz`仍会提升，并且可以访问`xyzSub`使用较短的限定字符串`thisNamespace.xyz.xyzSub`。</span><span class="sxs-lookup"><span data-stu-id="ef87b-119">However, class `xyz` is still promoted, and you can access `xyzSub` with the shorter qualification string `thisNamespace.xyz.xyzSub`.</span></span>  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a><span data-ttu-id="ef87b-120">分部类型的类型提升的失效</span><span class="sxs-lookup"><span data-stu-id="ef87b-120">Defeat of Type Promotion for Partial Types</span></span>  
 <span data-ttu-id="ef87b-121">如果类或结构在模块内的使用[分部](../../../../visual-basic/language-reference/modifiers/partial.md)关键字，类型提升会自动失效该类或结构，指示是否在命名空间不包含具有相同名称的成员。</span><span class="sxs-lookup"><span data-stu-id="ef87b-121">If a class or structure inside a module uses the [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) keyword, type promotion is automatically defeated for that class or structure, whether or not the namespace has a member with the same name.</span></span> <span data-ttu-id="ef87b-122">该模块中的其他元素都仍可进行类型提升。</span><span class="sxs-lookup"><span data-stu-id="ef87b-122">Other elements in the module are still eligible for type promotion.</span></span>  
  
 <span data-ttu-id="ef87b-123">**后果。**</span><span class="sxs-lookup"><span data-stu-id="ef87b-123">**Consequences.**</span></span> <span data-ttu-id="ef87b-124">意外的结果，甚至编译器错误，则可能会导致失败的部分定义的类型提升。</span><span class="sxs-lookup"><span data-stu-id="ef87b-124">Defeat of type promotion of a partial definition can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="ef87b-125">下面的示例演示主干分部定义的类，其中之一是在模块内。</span><span class="sxs-lookup"><span data-stu-id="ef87b-125">The following example shows skeleton partial definitions of a class, one of which is inside a module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#4)]  
  
 <span data-ttu-id="ef87b-126">在前面的示例中，开发人员可能希望编译器要合并的两个分部定义`sampleClass`。</span><span class="sxs-lookup"><span data-stu-id="ef87b-126">In the preceding example, the developer might expect the compiler to merge the two partial definitions of `sampleClass`.</span></span> <span data-ttu-id="ef87b-127">但是，编译器不考虑分部定义中的促销`sampleModule`。</span><span class="sxs-lookup"><span data-stu-id="ef87b-127">However, the compiler does not consider promotion for the partial definition inside `sampleModule`.</span></span> <span data-ttu-id="ef87b-128">因此，它会尝试编译两个单独且完全不同的类、 命名`sampleClass`但具有不同限定路径。</span><span class="sxs-lookup"><span data-stu-id="ef87b-128">As a result, it attempts to compile two separate and distinct classes, both named `sampleClass` but with different qualification paths.</span></span>  
  
 <span data-ttu-id="ef87b-129">仅当其完全限定的路径相同时，编译器才将合并分部定义。</span><span class="sxs-lookup"><span data-stu-id="ef87b-129">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="ef87b-130">建议</span><span class="sxs-lookup"><span data-stu-id="ef87b-130">Recommendations</span></span>  
 <span data-ttu-id="ef87b-131">下面的建议提供良好编程习惯。</span><span class="sxs-lookup"><span data-stu-id="ef87b-131">The following recommendations represent good programming practice.</span></span>  
  
-   <span data-ttu-id="ef87b-132">**唯一的名称。**</span><span class="sxs-lookup"><span data-stu-id="ef87b-132">**Unique Names.**</span></span> <span data-ttu-id="ef87b-133">在必须对编程元素的命名的完全控制，请始终是最好的场合使用唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="ef87b-133">When you have full control over the naming of programming elements, it is always a good idea to use unique names everywhere.</span></span> <span data-ttu-id="ef87b-134">相同的名称需要额外的限定，并且可以使代码难以阅读。</span><span class="sxs-lookup"><span data-stu-id="ef87b-134">Identical names require extra qualification and can make your code harder to read.</span></span> <span data-ttu-id="ef87b-135">它们还可能会导致细微错误和意外的结果。</span><span class="sxs-lookup"><span data-stu-id="ef87b-135">They can also lead to subtle errors and unexpected results.</span></span>  
  
-   <span data-ttu-id="ef87b-136">**完全限定。**</span><span class="sxs-lookup"><span data-stu-id="ef87b-136">**Full Qualification.**</span></span> <span data-ttu-id="ef87b-137">当你使用模块和相同的命名空间中的其他元素时，最安全的方法是始终使用完全限定的所有编程元素。</span><span class="sxs-lookup"><span data-stu-id="ef87b-137">When you are working with modules and other elements in the same namespace, the safest approach is to always use full qualification for all programming elements.</span></span> <span data-ttu-id="ef87b-138">如果类型提升大大降低模块成员，并且不完全限定的成员，可能会无意中访问不同的编程元素。</span><span class="sxs-lookup"><span data-stu-id="ef87b-138">If type promotion is defeated for a module member and you do not fully qualify that member, you could inadvertently access a different programming element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef87b-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef87b-139">See also</span></span>

- [<span data-ttu-id="ef87b-140">Module 语句</span><span class="sxs-lookup"><span data-stu-id="ef87b-140">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="ef87b-141">Namespace 语句</span><span class="sxs-lookup"><span data-stu-id="ef87b-141">Namespace Statement</span></span>](../../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="ef87b-142">Partial</span><span class="sxs-lookup"><span data-stu-id="ef87b-142">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)
- [<span data-ttu-id="ef87b-143">在 Visual Basic 中的作用域</span><span class="sxs-lookup"><span data-stu-id="ef87b-143">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="ef87b-144">如何：控制变量的作用域</span><span class="sxs-lookup"><span data-stu-id="ef87b-144">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [<span data-ttu-id="ef87b-145">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="ef87b-145">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
