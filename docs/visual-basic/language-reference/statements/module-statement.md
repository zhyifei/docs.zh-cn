---
title: Module 语句（Visual Basic）
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
ms.openlocfilehash: 9b1aae08d0009a9fd23d6441207f1601ffec2568
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583098"
---
# <a name="module-statement"></a><span data-ttu-id="7da0f-102">Module 语句</span><span class="sxs-lookup"><span data-stu-id="7da0f-102">Module Statement</span></span>

<span data-ttu-id="7da0f-103">声明模块的名称，并引入模块包含的变量、属性、事件和过程的定义。</span><span class="sxs-lookup"><span data-stu-id="7da0f-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>

## <a name="syntax"></a><span data-ttu-id="7da0f-104">语法</span><span class="sxs-lookup"><span data-stu-id="7da0f-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ]  Module name
    [ statements ]
End Module
```

## <a name="parts"></a><span data-ttu-id="7da0f-105">部件</span><span class="sxs-lookup"><span data-stu-id="7da0f-105">Parts</span></span>

`attributelist`  
<span data-ttu-id="7da0f-106">可选。</span><span class="sxs-lookup"><span data-stu-id="7da0f-106">Optional.</span></span> <span data-ttu-id="7da0f-107">请参阅[特性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="7da0f-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>

`accessmodifier`  
<span data-ttu-id="7da0f-108">可选。</span><span class="sxs-lookup"><span data-stu-id="7da0f-108">Optional.</span></span> <span data-ttu-id="7da0f-109">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="7da0f-109">Can be one of the following:</span></span>

- [<span data-ttu-id="7da0f-110">COMClassAttribute</span><span class="sxs-lookup"><span data-stu-id="7da0f-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

- [<span data-ttu-id="7da0f-111">Friend</span><span class="sxs-lookup"><span data-stu-id="7da0f-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

<span data-ttu-id="7da0f-112">请参阅 [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="7da0f-112">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

`name`  
<span data-ttu-id="7da0f-113">必须的。</span><span class="sxs-lookup"><span data-stu-id="7da0f-113">Required.</span></span> <span data-ttu-id="7da0f-114">此模块的名称。</span><span class="sxs-lookup"><span data-stu-id="7da0f-114">Name of this module.</span></span> <span data-ttu-id="7da0f-115">请参阅 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="7da0f-115">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

`statements`  
<span data-ttu-id="7da0f-116">可选。</span><span class="sxs-lookup"><span data-stu-id="7da0f-116">Optional.</span></span> <span data-ttu-id="7da0f-117">定义此模块的变量、属性、事件、过程和嵌套类型的语句。</span><span class="sxs-lookup"><span data-stu-id="7da0f-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>

`End Module`  
<span data-ttu-id="7da0f-118">终止 `Module` 定义。</span><span class="sxs-lookup"><span data-stu-id="7da0f-118">Terminates the `Module` definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="7da0f-119">备注</span><span class="sxs-lookup"><span data-stu-id="7da0f-119">Remarks</span></span>

<span data-ttu-id="7da0f-120">@No__t_0 语句定义一个在其命名空间中可用的引用类型。</span><span class="sxs-lookup"><span data-stu-id="7da0f-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="7da0f-121">*模块*（有时称为*标准模块*）与类相似，但有一些重要的区别。</span><span class="sxs-lookup"><span data-stu-id="7da0f-121">A *module* (sometimes called a *standard module*) is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="7da0f-122">每个模块都有一个实例，无需创建或分配给变量。</span><span class="sxs-lookup"><span data-stu-id="7da0f-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="7da0f-123">模块不支持继承或实现接口。</span><span class="sxs-lookup"><span data-stu-id="7da0f-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="7da0f-124">请注意，如果某个模块不是类或结构的*类型*，则不能将编程元素声明为具有模块的数据类型。</span><span class="sxs-lookup"><span data-stu-id="7da0f-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>

<span data-ttu-id="7da0f-125">只能在命名空间级别使用 `Module`。</span><span class="sxs-lookup"><span data-stu-id="7da0f-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="7da0f-126">这意味着模块的*声明上下文*必须是源文件或命名空间，不能是类、结构、模块、接口、过程或块。</span><span class="sxs-lookup"><span data-stu-id="7da0f-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="7da0f-127">不能将模块嵌套在其他模块或任何类型中。</span><span class="sxs-lookup"><span data-stu-id="7da0f-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="7da0f-128">有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="7da0f-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="7da0f-129">模块与程序具有相同的生存期。</span><span class="sxs-lookup"><span data-stu-id="7da0f-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="7da0f-130">因为其成员都是 `Shared` 的，所以它们的生存期也等于程序的生存期。</span><span class="sxs-lookup"><span data-stu-id="7da0f-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>

<span data-ttu-id="7da0f-131">模块默认为[Friend](../../../visual-basic/language-reference/modifiers/friend.md)访问。</span><span class="sxs-lookup"><span data-stu-id="7da0f-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span></span> <span data-ttu-id="7da0f-132">您可以使用访问修饰符调整其访问级别。</span><span class="sxs-lookup"><span data-stu-id="7da0f-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="7da0f-133">有关详细信息，请参阅[Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="7da0f-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="7da0f-134">模块的所有成员都隐式 `Shared`。</span><span class="sxs-lookup"><span data-stu-id="7da0f-134">All members of a module are implicitly `Shared`.</span></span>

## <a name="classes-and-modules"></a><span data-ttu-id="7da0f-135">类和模块</span><span class="sxs-lookup"><span data-stu-id="7da0f-135">Classes and Modules</span></span>

<span data-ttu-id="7da0f-136">这些元素具有许多相似之处，但也存在一些重要的差异。</span><span class="sxs-lookup"><span data-stu-id="7da0f-136">These elements have many similarities, but there are some important differences as well.</span></span>

- <span data-ttu-id="7da0f-137">**规范.**</span><span class="sxs-lookup"><span data-stu-id="7da0f-137">**Terminology.**</span></span> <span data-ttu-id="7da0f-138">Visual Basic 的早期版本可识别两种类型的模块：*类模块*（cls 文件）和*标准模块*（bas 文件）。</span><span class="sxs-lookup"><span data-stu-id="7da0f-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="7da0f-139">当前版本分别调用这些*类*和*模块*。</span><span class="sxs-lookup"><span data-stu-id="7da0f-139">The current version calls these *classes* and *modules*, respectively.</span></span>

- <span data-ttu-id="7da0f-140">**共享成员。**</span><span class="sxs-lookup"><span data-stu-id="7da0f-140">**Shared Members.**</span></span> <span data-ttu-id="7da0f-141">您可以控制某个类的成员是共享成员还是实例成员。</span><span class="sxs-lookup"><span data-stu-id="7da0f-141">You can control whether a member of a class is a shared or instance member.</span></span>

- <span data-ttu-id="7da0f-142">**对象方向。**</span><span class="sxs-lookup"><span data-stu-id="7da0f-142">**Object Orientation.**</span></span> <span data-ttu-id="7da0f-143">类是面向对象的，但模块不是。</span><span class="sxs-lookup"><span data-stu-id="7da0f-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="7da0f-144">因此，只有类可以实例化为对象。</span><span class="sxs-lookup"><span data-stu-id="7da0f-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="7da0f-145">有关详细信息，请参阅[对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="7da0f-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>

## <a name="rules"></a><span data-ttu-id="7da0f-146">规则</span><span class="sxs-lookup"><span data-stu-id="7da0f-146">Rules</span></span>

- <span data-ttu-id="7da0f-147">**组成.**</span><span class="sxs-lookup"><span data-stu-id="7da0f-147">**Modifiers.**</span></span> <span data-ttu-id="7da0f-148">所有模块成员都是隐式[共享](../../../visual-basic/language-reference/modifiers/shared.md)的。</span><span class="sxs-lookup"><span data-stu-id="7da0f-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="7da0f-149">在声明成员时，不能使用 `Shared` 关键字，也不能更改任何成员的共享状态。</span><span class="sxs-lookup"><span data-stu-id="7da0f-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>

- <span data-ttu-id="7da0f-150">**继承。**</span><span class="sxs-lookup"><span data-stu-id="7da0f-150">**Inheritance.**</span></span> <span data-ttu-id="7da0f-151">模块无法从所有模块继承的 <xref:System.Object> 以外的任何类型继承。</span><span class="sxs-lookup"><span data-stu-id="7da0f-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="7da0f-152">特别是，一个模块不能从另一个模块继承。</span><span class="sxs-lookup"><span data-stu-id="7da0f-152">In particular, one module cannot inherit from another.</span></span>

  <span data-ttu-id="7da0f-153">不能在模块定义中使用[Inherits 语句](../../../visual-basic/language-reference/statements/inherits-statement.md)，甚至可以指定 <xref:System.Object>。</span><span class="sxs-lookup"><span data-stu-id="7da0f-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>

- <span data-ttu-id="7da0f-154">**默认属性。**</span><span class="sxs-lookup"><span data-stu-id="7da0f-154">**Default Property.**</span></span> <span data-ttu-id="7da0f-155">不能在模块中定义任何默认属性。</span><span class="sxs-lookup"><span data-stu-id="7da0f-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="7da0f-156">有关详细信息，请参阅[默认值](../../../visual-basic/language-reference/modifiers/default.md)。</span><span class="sxs-lookup"><span data-stu-id="7da0f-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span></span>

## <a name="behavior"></a><span data-ttu-id="7da0f-157">行为</span><span class="sxs-lookup"><span data-stu-id="7da0f-157">Behavior</span></span>

- <span data-ttu-id="7da0f-158">**访问级别。**</span><span class="sxs-lookup"><span data-stu-id="7da0f-158">**Access Level.**</span></span> <span data-ttu-id="7da0f-159">在模块中，你可以使用其自己的访问级别声明每个成员。</span><span class="sxs-lookup"><span data-stu-id="7da0f-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="7da0f-160">模块成员默认为[公共](../../../visual-basic/language-reference/modifiers/public.md)访问权限，变量和常量除外，默认为[私有](../../../visual-basic/language-reference/modifiers/private.md)访问。</span><span class="sxs-lookup"><span data-stu-id="7da0f-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span></span> <span data-ttu-id="7da0f-161">当某个模块的访问权限超过其成员之一时，将优先使用指定的模块访问级别。</span><span class="sxs-lookup"><span data-stu-id="7da0f-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>

- <span data-ttu-id="7da0f-162">**内.**</span><span class="sxs-lookup"><span data-stu-id="7da0f-162">**Scope.**</span></span> <span data-ttu-id="7da0f-163">模块在其命名空间中的作用域。</span><span class="sxs-lookup"><span data-stu-id="7da0f-163">A module is in scope throughout its namespace.</span></span>

  <span data-ttu-id="7da0f-164">每个模块成员的作用域都是整个模块。</span><span class="sxs-lookup"><span data-stu-id="7da0f-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="7da0f-165">请注意，所有成员都接受*类型提升*，这会导致其作用域升级到包含该模块的命名空间。</span><span class="sxs-lookup"><span data-stu-id="7da0f-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="7da0f-166">有关详细信息，请参阅[类型提升](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)。</span><span class="sxs-lookup"><span data-stu-id="7da0f-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>

- <span data-ttu-id="7da0f-167">**限定.**</span><span class="sxs-lookup"><span data-stu-id="7da0f-167">**Qualification.**</span></span> <span data-ttu-id="7da0f-168">项目中可以有多个模块，可以在两个或多个模块中声明同名的成员。</span><span class="sxs-lookup"><span data-stu-id="7da0f-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="7da0f-169">但是，如果引用来自模块外部，则必须使用适当的模块名称来限定对此类成员的任何引用。</span><span class="sxs-lookup"><span data-stu-id="7da0f-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="7da0f-170">有关详细信息，请参阅 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="7da0f-170">For more information, see [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

## <a name="example"></a><span data-ttu-id="7da0f-171">示例</span><span class="sxs-lookup"><span data-stu-id="7da0f-171">Example</span></span>

[!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]

## <a name="see-also"></a><span data-ttu-id="7da0f-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="7da0f-172">See also</span></span>

- [<span data-ttu-id="7da0f-173">Class 语句</span><span class="sxs-lookup"><span data-stu-id="7da0f-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="7da0f-174">Namespace 语句</span><span class="sxs-lookup"><span data-stu-id="7da0f-174">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="7da0f-175">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="7da0f-175">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="7da0f-176">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="7da0f-176">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="7da0f-177">Property 语句</span><span class="sxs-lookup"><span data-stu-id="7da0f-177">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="7da0f-178">类型提升</span><span class="sxs-lookup"><span data-stu-id="7da0f-178">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
