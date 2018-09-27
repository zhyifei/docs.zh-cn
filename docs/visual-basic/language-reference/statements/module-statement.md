---
title: Module 语句 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 5628224a08fe5f12cf2a81b179c4998001174354
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47237327"
---
# <a name="module-statement"></a><span data-ttu-id="c4ec1-102">Module 语句</span><span class="sxs-lookup"><span data-stu-id="c4ec1-102">Module Statement</span></span>
<span data-ttu-id="c4ec1-103">声明模块的名称，并引入的变量、 属性、 事件和该模块包含的过程的定义。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4ec1-104">语法</span><span class="sxs-lookup"><span data-stu-id="c4ec1-104">Syntax</span></span>  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a><span data-ttu-id="c4ec1-105">部件</span><span class="sxs-lookup"><span data-stu-id="c4ec1-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="c4ec1-106">可选。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-106">Optional.</span></span> <span data-ttu-id="c4ec1-107">请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="c4ec1-108">可选。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-108">Optional.</span></span> <span data-ttu-id="c4ec1-109">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="c4ec1-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="c4ec1-110">Public</span><span class="sxs-lookup"><span data-stu-id="c4ec1-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [<span data-ttu-id="c4ec1-111">Friend</span><span class="sxs-lookup"><span data-stu-id="c4ec1-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 <span data-ttu-id="c4ec1-112">请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-112">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `name`  
 <span data-ttu-id="c4ec1-113">必须的。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-113">Required.</span></span> <span data-ttu-id="c4ec1-114">此模块的名称。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-114">Name of this module.</span></span> <span data-ttu-id="c4ec1-115">请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-115">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `statements`  
 <span data-ttu-id="c4ec1-116">可选。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-116">Optional.</span></span> <span data-ttu-id="c4ec1-117">定义变量、 属性、 事件、 过程和嵌套的类型，此模块的语句。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>  
  
 `End Module`  
 <span data-ttu-id="c4ec1-118">终止`Module`定义。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-118">Terminates the `Module` definition.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4ec1-119">备注</span><span class="sxs-lookup"><span data-stu-id="c4ec1-119">Remarks</span></span>  
 <span data-ttu-id="c4ec1-120">一个`Module`语句定义在整个命名空间中可用的引用类型。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="c4ec1-121">一个*模块*(有时称为*标准模块*) 类似于类，但有一些重要的差别。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-121">A *module* (sometimes called a *standard module*)is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="c4ec1-122">每个模块都有且只有一个实例，并不需要创建或分配给一个变量。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="c4ec1-123">模块不支持继承或实现接口。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="c4ec1-124">请注意，模块并不*类型*类或结构是在意义上，不能声明为具有模块的数据类型的编程元素。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>  
  
 <span data-ttu-id="c4ec1-125">可以使用`Module`仅在命名空间级别。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="c4ec1-126">这意味着*声明上下文*供模块必须的源文件或命名空间，并且不能为类、 结构、 模块、 接口、 过程或块。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="c4ec1-127">不能嵌套在另一个模块，或在任何类型的模块。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="c4ec1-128">有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="c4ec1-129">模块具有相同的生存期为您的程序。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="c4ec1-130">因为其成员是所有`Shared`，它们还具有相同的程序的生存期。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>  
  
 <span data-ttu-id="c4ec1-131">默认为模块[友元](../../../visual-basic/language-reference/modifiers/friend.md)访问。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span></span> <span data-ttu-id="c4ec1-132">您可以调整其访问级别和访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="c4ec1-133">有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="c4ec1-134">模块的所有成员都都隐式`Shared`。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-134">All members of a module are implicitly `Shared`.</span></span>  
  
## <a name="classes-and-modules"></a><span data-ttu-id="c4ec1-135">类和模块</span><span class="sxs-lookup"><span data-stu-id="c4ec1-135">Classes and Modules</span></span>  
 <span data-ttu-id="c4ec1-136">这些元素具有许多相似之处，但有一些重要的差异。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-136">These elements have many similarities, but there are some important differences as well.</span></span>  
  
-   <span data-ttu-id="c4ec1-137">**术语。**</span><span class="sxs-lookup"><span data-stu-id="c4ec1-137">**Terminology.**</span></span> <span data-ttu-id="c4ec1-138">以前版本的 Visual Basic 识别两种类型的模块：*类模块*（.cls 文件） 和*标准模块*（.bas 文件）。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="c4ec1-139">当前版本调用这些*类*并*模块*分别。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-139">The current version calls these *classes* and *modules*, respectively.</span></span>  
  
-   <span data-ttu-id="c4ec1-140">**共享的成员。**</span><span class="sxs-lookup"><span data-stu-id="c4ec1-140">**Shared Members.**</span></span> <span data-ttu-id="c4ec1-141">您可以控制是否在不共享类的成员或实例成员。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-141">You can control whether a member of a class is a shared or instance member.</span></span>  
  
-   <span data-ttu-id="c4ec1-142">**面向对象。**</span><span class="sxs-lookup"><span data-stu-id="c4ec1-142">**Object Orientation.**</span></span> <span data-ttu-id="c4ec1-143">类是面向对象的但不是模块。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="c4ec1-144">因此，只能将类可以为对象实例化。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="c4ec1-145">有关详细信息，请参阅[对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="c4ec1-146">规则</span><span class="sxs-lookup"><span data-stu-id="c4ec1-146">Rules</span></span>  
  
-   <span data-ttu-id="c4ec1-147">**修饰符。**</span><span class="sxs-lookup"><span data-stu-id="c4ec1-147">**Modifiers.**</span></span> <span data-ttu-id="c4ec1-148">所有模块成员都为隐式[共享](../../../visual-basic/language-reference/modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="c4ec1-149">不能使用`Shared`关键字时声明一个成员，并且您不能更改任何成员的共享的状态。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>  
  
-   <span data-ttu-id="c4ec1-150">**继承。**</span><span class="sxs-lookup"><span data-stu-id="c4ec1-150">**Inheritance.**</span></span> <span data-ttu-id="c4ec1-151">而不从任何类型继承一个模块，不能<xref:System.Object>，哪些所有模块从继承。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="c4ec1-152">具体而言，不能从另一个继承一个模块。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-152">In particular, one module cannot inherit from another.</span></span>  
  
     <span data-ttu-id="c4ec1-153">不能使用[Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md)在模块定义中，甚至指定<xref:System.Object>。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>  
  
-   <span data-ttu-id="c4ec1-154">**默认属性。**</span><span class="sxs-lookup"><span data-stu-id="c4ec1-154">**Default Property.**</span></span> <span data-ttu-id="c4ec1-155">您不能在模块中定义的任何默认属性。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="c4ec1-156">有关详细信息，请参阅[默认](../../../visual-basic/language-reference/modifiers/default.md)。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="c4ec1-157">行为</span><span class="sxs-lookup"><span data-stu-id="c4ec1-157">Behavior</span></span>  
  
-   <span data-ttu-id="c4ec1-158">**访问级别。**</span><span class="sxs-lookup"><span data-stu-id="c4ec1-158">**Access Level.**</span></span> <span data-ttu-id="c4ec1-159">在模块中，可以声明具有其自己的访问级别的每个成员。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="c4ec1-160">模块成员默认为[公共](../../../visual-basic/language-reference/modifiers/public.md)访问，除变量和常量、 到哪些默认[专用](../../../visual-basic/language-reference/modifiers/private.md)访问。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span></span> <span data-ttu-id="c4ec1-161">当模块具有比其成员之一的限制性更强的访问时，指定的模块的访问级别将优先。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>  
  
-   <span data-ttu-id="c4ec1-162">**作用域。**</span><span class="sxs-lookup"><span data-stu-id="c4ec1-162">**Scope.**</span></span> <span data-ttu-id="c4ec1-163">模块是在整个命名空间范围内。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-163">A module is in scope throughout its namespace.</span></span>  
  
     <span data-ttu-id="c4ec1-164">每个模块成员的作用域是整个模块。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="c4ec1-165">请注意，所有成员都会都经受*类型提升*，这将导致它们提升到包含该模块的命名空间的范围。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="c4ec1-166">有关详细信息，请参阅[类型提升](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
-   <span data-ttu-id="c4ec1-167">**限定。**</span><span class="sxs-lookup"><span data-stu-id="c4ec1-167">**Qualification.**</span></span> <span data-ttu-id="c4ec1-168">您可以在项目中，有多个模块，而您可以声明具有两个或多个模块中具有相同名称的成员。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="c4ec1-169">但是，如果引用是从外部该模块必须限定对此类成员具有适当的模块名称的任何引用。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="c4ec1-170">有关详细信息，请参阅[References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4ec1-170">For more information, see [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4ec1-171">示例</span><span class="sxs-lookup"><span data-stu-id="c4ec1-171">Example</span></span>  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c4ec1-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4ec1-172">See Also</span></span>  
 [<span data-ttu-id="c4ec1-173">Class 语句</span><span class="sxs-lookup"><span data-stu-id="c4ec1-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="c4ec1-174">Namespace 语句</span><span class="sxs-lookup"><span data-stu-id="c4ec1-174">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="c4ec1-175">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="c4ec1-175">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="c4ec1-176">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="c4ec1-176">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="c4ec1-177">Property 语句</span><span class="sxs-lookup"><span data-stu-id="c4ec1-177">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="c4ec1-178">类型提升</span><span class="sxs-lookup"><span data-stu-id="c4ec1-178">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
