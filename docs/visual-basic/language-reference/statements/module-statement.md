---
title: Module 语句
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 51f8fd063449c072a69cdffd9f6ce2a96cc3f68c
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="module-statement"></a><span data-ttu-id="747f0-102">Module 语句</span><span class="sxs-lookup"><span data-stu-id="747f0-102">Module Statement</span></span>
<span data-ttu-id="747f0-103">声明的模块的名称，并引入的变量、 属性、 事件和模块包含的过程的定义。</span><span class="sxs-lookup"><span data-stu-id="747f0-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="747f0-104">语法</span><span class="sxs-lookup"><span data-stu-id="747f0-104">Syntax</span></span>  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a><span data-ttu-id="747f0-105">部件</span><span class="sxs-lookup"><span data-stu-id="747f0-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="747f0-106">可选。</span><span class="sxs-lookup"><span data-stu-id="747f0-106">Optional.</span></span> <span data-ttu-id="747f0-107">请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="747f0-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="747f0-108">可选。</span><span class="sxs-lookup"><span data-stu-id="747f0-108">Optional.</span></span> <span data-ttu-id="747f0-109">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="747f0-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="747f0-110">Public</span><span class="sxs-lookup"><span data-stu-id="747f0-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [<span data-ttu-id="747f0-111">Friend</span><span class="sxs-lookup"><span data-stu-id="747f0-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 <span data-ttu-id="747f0-112">请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="747f0-112">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `name`  
 <span data-ttu-id="747f0-113">必须的。</span><span class="sxs-lookup"><span data-stu-id="747f0-113">Required.</span></span> <span data-ttu-id="747f0-114">此模块的名称。</span><span class="sxs-lookup"><span data-stu-id="747f0-114">Name of this module.</span></span> <span data-ttu-id="747f0-115">请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="747f0-115">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `statements`  
 <span data-ttu-id="747f0-116">可选。</span><span class="sxs-lookup"><span data-stu-id="747f0-116">Optional.</span></span> <span data-ttu-id="747f0-117">定义变量、 属性、 事件、 过程和嵌套的类型，此模块的语句。</span><span class="sxs-lookup"><span data-stu-id="747f0-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>  
  
 `End Module`  
 <span data-ttu-id="747f0-118">终止`Module`定义。</span><span class="sxs-lookup"><span data-stu-id="747f0-118">Terminates the `Module` definition.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="747f0-119">备注</span><span class="sxs-lookup"><span data-stu-id="747f0-119">Remarks</span></span>  
 <span data-ttu-id="747f0-120">A`Module`语句定义引用类型可在其命名空间可用。</span><span class="sxs-lookup"><span data-stu-id="747f0-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="747f0-121">A*模块*(有时称为*标准模块*) 类似于类，但有一些重要区别。</span><span class="sxs-lookup"><span data-stu-id="747f0-121">A *module* (sometimes called a *standard module*)is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="747f0-122">每个模块具有恰好一个实例，不需要创建或分配给变量。</span><span class="sxs-lookup"><span data-stu-id="747f0-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="747f0-123">模块不支持继承或实现接口。</span><span class="sxs-lookup"><span data-stu-id="747f0-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="747f0-124">请注意，模块不是*类型*在类或结构的意义上，你不能声明为具有模块的数据类型的编程元素。</span><span class="sxs-lookup"><span data-stu-id="747f0-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>  
  
 <span data-ttu-id="747f0-125">你可以使用`Module`只能在命名空间级别。</span><span class="sxs-lookup"><span data-stu-id="747f0-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="747f0-126">这意味着*声明上下文*模块必须为源文件或命名空间，并且不能为类、 结构、 模块、 接口、 过程或块。</span><span class="sxs-lookup"><span data-stu-id="747f0-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="747f0-127">不能嵌套在另一个模块内的任何类型或模块。</span><span class="sxs-lookup"><span data-stu-id="747f0-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="747f0-128">有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="747f0-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="747f0-129">模块具有程序相同的生存期。</span><span class="sxs-lookup"><span data-stu-id="747f0-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="747f0-130">因为所有其成员`Shared`，它们还具有相等的程序的生存期。</span><span class="sxs-lookup"><span data-stu-id="747f0-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>  
  
 <span data-ttu-id="747f0-131">模块默认为[友元](../../../visual-basic/language-reference/modifiers/friend.md)访问。</span><span class="sxs-lookup"><span data-stu-id="747f0-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span></span> <span data-ttu-id="747f0-132">你可以调整其访问级别有访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="747f0-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="747f0-133">有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="747f0-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="747f0-134">模块的所有成员都都隐式`Shared`。</span><span class="sxs-lookup"><span data-stu-id="747f0-134">All members of a module are implicitly `Shared`.</span></span>  
  
## <a name="classes-and-modules"></a><span data-ttu-id="747f0-135">类和模块</span><span class="sxs-lookup"><span data-stu-id="747f0-135">Classes and Modules</span></span>  
 <span data-ttu-id="747f0-136">这些元素包含的许多相似之处，但有一些重要的区别。</span><span class="sxs-lookup"><span data-stu-id="747f0-136">These elements have many similarities, but there are some important differences as well.</span></span>  
  
-   <span data-ttu-id="747f0-137">**术语。**</span><span class="sxs-lookup"><span data-stu-id="747f0-137">**Terminology.**</span></span> <span data-ttu-id="747f0-138">Visual Basic 早期版本识别两种类型的模块：*类模块*（.cls 文件） 和*标准模块*（.bas 文件）。</span><span class="sxs-lookup"><span data-stu-id="747f0-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="747f0-139">当前版本调用这些*类*和*模块*分别。</span><span class="sxs-lookup"><span data-stu-id="747f0-139">The current version calls these *classes* and *modules*, respectively.</span></span>  
  
-   <span data-ttu-id="747f0-140">**共享的成员。**</span><span class="sxs-lookup"><span data-stu-id="747f0-140">**Shared Members.**</span></span> <span data-ttu-id="747f0-141">你可以控制类的成员是共享成员还是实例成员。</span><span class="sxs-lookup"><span data-stu-id="747f0-141">You can control whether a member of a class is a shared or instance member.</span></span>  
  
-   <span data-ttu-id="747f0-142">**面向对象。**</span><span class="sxs-lookup"><span data-stu-id="747f0-142">**Object Orientation.**</span></span> <span data-ttu-id="747f0-143">类是面向对象的但模块不是。</span><span class="sxs-lookup"><span data-stu-id="747f0-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="747f0-144">因此，只能将类可以将实例化为对象。</span><span class="sxs-lookup"><span data-stu-id="747f0-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="747f0-145">有关详细信息，请参阅[对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="747f0-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="747f0-146">规则</span><span class="sxs-lookup"><span data-stu-id="747f0-146">Rules</span></span>  
  
-   <span data-ttu-id="747f0-147">**修饰符。**</span><span class="sxs-lookup"><span data-stu-id="747f0-147">**Modifiers.**</span></span> <span data-ttu-id="747f0-148">所有的模块成员为隐式[共享](../../../visual-basic/language-reference/modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="747f0-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="747f0-149">不能使用`Shared`关键字时声明成员，并且你无法更改任何成员的共享的状态。</span><span class="sxs-lookup"><span data-stu-id="747f0-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>  
  
-   <span data-ttu-id="747f0-150">**继承。**</span><span class="sxs-lookup"><span data-stu-id="747f0-150">**Inheritance.**</span></span> <span data-ttu-id="747f0-151">模块不能从继承任何类型以外<xref:System.Object>，哪些所有模块从继承。</span><span class="sxs-lookup"><span data-stu-id="747f0-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="747f0-152">具体而言，一个模块不能继承自另一个。</span><span class="sxs-lookup"><span data-stu-id="747f0-152">In particular, one module cannot inherit from another.</span></span>  
  
     <span data-ttu-id="747f0-153">不能使用[继承语句](../../../visual-basic/language-reference/statements/inherits-statement.md)在模块定义中，即使指定<xref:System.Object>。</span><span class="sxs-lookup"><span data-stu-id="747f0-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>  
  
-   <span data-ttu-id="747f0-154">**默认属性。**</span><span class="sxs-lookup"><span data-stu-id="747f0-154">**Default Property.**</span></span> <span data-ttu-id="747f0-155">不能在模块中定义的任何默认属性。</span><span class="sxs-lookup"><span data-stu-id="747f0-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="747f0-156">有关详细信息，请参阅[默认](../../../visual-basic/language-reference/modifiers/default.md)。</span><span class="sxs-lookup"><span data-stu-id="747f0-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="747f0-157">行为</span><span class="sxs-lookup"><span data-stu-id="747f0-157">Behavior</span></span>  
  
-   <span data-ttu-id="747f0-158">**访问级别。**</span><span class="sxs-lookup"><span data-stu-id="747f0-158">**Access Level.**</span></span> <span data-ttu-id="747f0-159">在模块中，你可以声明每个成员使用其自己的访问级别。</span><span class="sxs-lookup"><span data-stu-id="747f0-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="747f0-160">模块成员默认为[公共](../../../visual-basic/language-reference/modifiers/public.md)访问，除变量和常量，哪些默认为[私有](../../../visual-basic/language-reference/modifiers/private.md)访问。</span><span class="sxs-lookup"><span data-stu-id="747f0-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span></span> <span data-ttu-id="747f0-161">如果模块具有相比限制更多访问其成员之一，指定的模块访问级别优先。</span><span class="sxs-lookup"><span data-stu-id="747f0-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>  
  
-   <span data-ttu-id="747f0-162">**作用域。**</span><span class="sxs-lookup"><span data-stu-id="747f0-162">**Scope.**</span></span> <span data-ttu-id="747f0-163">模块是在整个命名空间范围内。</span><span class="sxs-lookup"><span data-stu-id="747f0-163">A module is in scope throughout its namespace.</span></span>  
  
     <span data-ttu-id="747f0-164">每个模块成员的作用域是整个模块。</span><span class="sxs-lookup"><span data-stu-id="747f0-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="747f0-165">请注意，所有成员都会都经受*类型提升*，这将导致它们提升为包含该模块的命名空间的范围。</span><span class="sxs-lookup"><span data-stu-id="747f0-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="747f0-166">有关详细信息，请参阅[类型提升](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)。</span><span class="sxs-lookup"><span data-stu-id="747f0-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
-   <span data-ttu-id="747f0-167">**限定。**</span><span class="sxs-lookup"><span data-stu-id="747f0-167">**Qualification.**</span></span> <span data-ttu-id="747f0-168">你可以在项目中，有多个模块，你可以声明具有两个或多个模块中的同名成员。</span><span class="sxs-lookup"><span data-stu-id="747f0-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="747f0-169">但是，如果从该模块以外的引用为必须限定对具有适当的模块名称的此类的成员的任何引用。</span><span class="sxs-lookup"><span data-stu-id="747f0-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="747f0-170">有关详细信息，请参阅[对声明的元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="747f0-170">For more information, see [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="747f0-171">示例</span><span class="sxs-lookup"><span data-stu-id="747f0-171">Example</span></span>  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="747f0-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="747f0-172">See Also</span></span>  
 [<span data-ttu-id="747f0-173">Class 语句</span><span class="sxs-lookup"><span data-stu-id="747f0-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="747f0-174">Namespace 语句</span><span class="sxs-lookup"><span data-stu-id="747f0-174">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="747f0-175">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="747f0-175">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="747f0-176">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="747f0-176">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="747f0-177">Property 语句</span><span class="sxs-lookup"><span data-stu-id="747f0-177">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="747f0-178">类型提升</span><span class="sxs-lookup"><span data-stu-id="747f0-178">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
