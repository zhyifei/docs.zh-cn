---
title: Property Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
caps.latest.revision: 41
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 558b62dd8c676532355ef12134ad8cb803b70796
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="property-statement"></a><span data-ttu-id="19cfa-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="19cfa-102">Property Statement</span></span>
<span data-ttu-id="19cfa-103">声明的属性，以及用于存储和检索属性的值的属性过程的名称。</span><span class="sxs-lookup"><span data-stu-id="19cfa-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19cfa-104">语法</span><span class="sxs-lookup"><span data-stu-id="19cfa-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]  
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
    [ <attributelist> ] [ accessmodifier ] Get  
        [ statements ]  
    End Get  
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )  
        [ statements ]  
    End Set  
End Property  
- or -  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]   
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
```  
  
## <a name="parts"></a><span data-ttu-id="19cfa-105">部件</span><span class="sxs-lookup"><span data-stu-id="19cfa-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="19cfa-106">可选。</span><span class="sxs-lookup"><span data-stu-id="19cfa-106">Optional.</span></span> <span data-ttu-id="19cfa-107">将应用于此属性的属性列表或`Get`或`Set`过程。</span><span class="sxs-lookup"><span data-stu-id="19cfa-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="19cfa-108">请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="19cfa-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `Default`  
  
     <span data-ttu-id="19cfa-109">可选。</span><span class="sxs-lookup"><span data-stu-id="19cfa-109">Optional.</span></span> <span data-ttu-id="19cfa-110">指定此属性是类或结构定义它的默认属性。</span><span class="sxs-lookup"><span data-stu-id="19cfa-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="19cfa-111">默认属性必须接受参数并可以设置和检索，而不必指定属性名称。</span><span class="sxs-lookup"><span data-stu-id="19cfa-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="19cfa-112">如果声明属性作为`Default`，不能使用`Private`的属性上或其属性过程中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="19cfa-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="19cfa-113">上是可选的`Property`语句和上最多一种`Get`和`Set`语句。</span><span class="sxs-lookup"><span data-stu-id="19cfa-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="19cfa-114">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="19cfa-114">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="19cfa-115">Public</span><span class="sxs-lookup"><span data-stu-id="19cfa-115">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="19cfa-116">Protected</span><span class="sxs-lookup"><span data-stu-id="19cfa-116">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="19cfa-117">Friend</span><span class="sxs-lookup"><span data-stu-id="19cfa-117">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="19cfa-118">Private</span><span class="sxs-lookup"><span data-stu-id="19cfa-118">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="19cfa-119">请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="19cfa-119">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `propertymodifiers`  
  
     <span data-ttu-id="19cfa-120">可选。</span><span class="sxs-lookup"><span data-stu-id="19cfa-120">Optional.</span></span> <span data-ttu-id="19cfa-121">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="19cfa-121">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="19cfa-122">重载</span><span class="sxs-lookup"><span data-stu-id="19cfa-122">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="19cfa-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="19cfa-123">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="19cfa-124">Overridable</span><span class="sxs-lookup"><span data-stu-id="19cfa-124">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="19cfa-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="19cfa-125">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="19cfa-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="19cfa-126">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="19cfa-127">可选。</span><span class="sxs-lookup"><span data-stu-id="19cfa-127">Optional.</span></span> <span data-ttu-id="19cfa-128">请参阅[共享](../../../visual-basic/language-reference/modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="19cfa-128">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="19cfa-129">可选。</span><span class="sxs-lookup"><span data-stu-id="19cfa-129">Optional.</span></span> <span data-ttu-id="19cfa-130">请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。</span><span class="sxs-lookup"><span data-stu-id="19cfa-130">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="19cfa-131">可选。</span><span class="sxs-lookup"><span data-stu-id="19cfa-131">Optional.</span></span> <span data-ttu-id="19cfa-132">请参阅[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="19cfa-132">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WriteOnly`  
  
     <span data-ttu-id="19cfa-133">可选。</span><span class="sxs-lookup"><span data-stu-id="19cfa-133">Optional.</span></span> <span data-ttu-id="19cfa-134">请参阅[WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)。</span><span class="sxs-lookup"><span data-stu-id="19cfa-134">See [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="19cfa-135">可选。</span><span class="sxs-lookup"><span data-stu-id="19cfa-135">Optional.</span></span> <span data-ttu-id="19cfa-136">请参阅[迭代器](../../../visual-basic/language-reference/modifiers/iterator.md)。</span><span class="sxs-lookup"><span data-stu-id="19cfa-136">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="19cfa-137">必须的。</span><span class="sxs-lookup"><span data-stu-id="19cfa-137">Required.</span></span> <span data-ttu-id="19cfa-138">属性的名称。</span><span class="sxs-lookup"><span data-stu-id="19cfa-138">Name of the property.</span></span> <span data-ttu-id="19cfa-139">请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="19cfa-139">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="19cfa-140">可选。</span><span class="sxs-lookup"><span data-stu-id="19cfa-140">Optional.</span></span> <span data-ttu-id="19cfa-141">表示此属性的参数和可能具有的其他参数的本地变量名的列表`Set`过程。</span><span class="sxs-lookup"><span data-stu-id="19cfa-141">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="19cfa-142">请参阅[参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)。</span><span class="sxs-lookup"><span data-stu-id="19cfa-142">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="19cfa-143">如果存在`Option``Strict`是`On`。</span><span class="sxs-lookup"><span data-stu-id="19cfa-143">Required if `Option``Strict` is `On`.</span></span> <span data-ttu-id="19cfa-144">返回此属性的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="19cfa-144">Data type of the value returned by this property.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="19cfa-145">可选。</span><span class="sxs-lookup"><span data-stu-id="19cfa-145">Optional.</span></span> <span data-ttu-id="19cfa-146">指示此属性实现一个或多个属性，此属性包含的类或结构实现接口中定义的每个组。</span><span class="sxs-lookup"><span data-stu-id="19cfa-146">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="19cfa-147">请参阅[实现语句](../../../visual-basic/language-reference/statements/implements-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="19cfa-147">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="19cfa-148">如果提供 `Implements`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="19cfa-148">Required if `Implements` is supplied.</span></span> <span data-ttu-id="19cfa-149">正在实现的属性的列表。</span><span class="sxs-lookup"><span data-stu-id="19cfa-149">List of properties being implemented.</span></span>  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     <span data-ttu-id="19cfa-150">每个 `implementedproperty` 都具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="19cfa-150">Each `implementedproperty` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="19cfa-151">部件</span><span class="sxs-lookup"><span data-stu-id="19cfa-151">Part</span></span>|<span data-ttu-id="19cfa-152">描述</span><span class="sxs-lookup"><span data-stu-id="19cfa-152">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="19cfa-153">必须的。</span><span class="sxs-lookup"><span data-stu-id="19cfa-153">Required.</span></span> <span data-ttu-id="19cfa-154">包含此属性实现的接口名称的类或结构。</span><span class="sxs-lookup"><span data-stu-id="19cfa-154">Name of an interface implemented by this property's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="19cfa-155">必须的。</span><span class="sxs-lookup"><span data-stu-id="19cfa-155">Required.</span></span> <span data-ttu-id="19cfa-156">中定义的属性的名称`interface`。</span><span class="sxs-lookup"><span data-stu-id="19cfa-156">Name by which the property is defined in `interface`.</span></span>|  
  
-   `Get`  
  
     <span data-ttu-id="19cfa-157">可选。</span><span class="sxs-lookup"><span data-stu-id="19cfa-157">Optional.</span></span> <span data-ttu-id="19cfa-158">所需属性如果标记`WriteOnly`。</span><span class="sxs-lookup"><span data-stu-id="19cfa-158">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="19cfa-159">启动`Get`用于返回属性的值的属性过程。</span><span class="sxs-lookup"><span data-stu-id="19cfa-159">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  
  
-   `statements`  
  
     <span data-ttu-id="19cfa-160">可选。</span><span class="sxs-lookup"><span data-stu-id="19cfa-160">Optional.</span></span> <span data-ttu-id="19cfa-161">要在中运行的语句块`Get`或`Set`过程。</span><span class="sxs-lookup"><span data-stu-id="19cfa-161">Block of statements to run within the `Get` or `Set` procedure.</span></span>  
  
-   `End Get`  
  
     <span data-ttu-id="19cfa-162">终止`Get`属性过程。</span><span class="sxs-lookup"><span data-stu-id="19cfa-162">Terminates the `Get` property procedure.</span></span>  
  
-   `Set`  
  
     <span data-ttu-id="19cfa-163">可选。</span><span class="sxs-lookup"><span data-stu-id="19cfa-163">Optional.</span></span> <span data-ttu-id="19cfa-164">所需属性如果标记`ReadOnly`。</span><span class="sxs-lookup"><span data-stu-id="19cfa-164">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="19cfa-165">启动`Set`用于存储属性的值的属性过程。</span><span class="sxs-lookup"><span data-stu-id="19cfa-165">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  
  
-   `End Set`  
  
     <span data-ttu-id="19cfa-166">终止`Set`属性过程。</span><span class="sxs-lookup"><span data-stu-id="19cfa-166">Terminates the `Set` property procedure.</span></span>  
  
-   `End Property`  
  
     <span data-ttu-id="19cfa-167">终止此属性的定义。</span><span class="sxs-lookup"><span data-stu-id="19cfa-167">Terminates the definition of this property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19cfa-168">备注</span><span class="sxs-lookup"><span data-stu-id="19cfa-168">Remarks</span></span>  
 <span data-ttu-id="19cfa-169">`Property`语句会引入属性声明。</span><span class="sxs-lookup"><span data-stu-id="19cfa-169">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="19cfa-170">属性可以具有`Get`过程 （只读），`Set`过程 （只写） 或二者 （读写）。</span><span class="sxs-lookup"><span data-stu-id="19cfa-170">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="19cfa-171">可以省略`Get`和`Set`过程时使用一个自动实现的属性。</span><span class="sxs-lookup"><span data-stu-id="19cfa-171">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="19cfa-172">有关详细信息，请参阅[自动实现的属性](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="19cfa-172">For more information, see [Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="19cfa-173">你可以使用`Property`只能在类级别。</span><span class="sxs-lookup"><span data-stu-id="19cfa-173">You can use `Property` only at class level.</span></span> <span data-ttu-id="19cfa-174">这意味着*声明上下文*属性必须为类、 结构、 模块或接口，并且不能是源文件、 命名空间、 过程中或块。</span><span class="sxs-lookup"><span data-stu-id="19cfa-174">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="19cfa-175">有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="19cfa-175">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="19cfa-176">默认情况下，属性使用公共访问权限。</span><span class="sxs-lookup"><span data-stu-id="19cfa-176">By default, properties use public access.</span></span> <span data-ttu-id="19cfa-177">可以调整使用访问修饰符的属性的访问级别`Property`语句，然后你可以选择性地调整其一个属性过程限制性更强的访问级别。</span><span class="sxs-lookup"><span data-stu-id="19cfa-177">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>  
  
 <span data-ttu-id="19cfa-178">Visual Basic 将传递到参数`Set`属性分配期间的过程。</span><span class="sxs-lookup"><span data-stu-id="19cfa-178">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="19cfa-179">如果未提供的参数`Set`，集成的开发环境 (IDE) 使用名为的隐式参数`value`。</span><span class="sxs-lookup"><span data-stu-id="19cfa-179">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="19cfa-180">此参数包含要分配给属性的值。</span><span class="sxs-lookup"><span data-stu-id="19cfa-180">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="19cfa-181">通常将此值存储在专用的本地变量，并将其返回每当`Get`调用过程。</span><span class="sxs-lookup"><span data-stu-id="19cfa-181">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="19cfa-182">规则</span><span class="sxs-lookup"><span data-stu-id="19cfa-182">Rules</span></span>  
  
-   <span data-ttu-id="19cfa-183">**混合的访问级别。**</span><span class="sxs-lookup"><span data-stu-id="19cfa-183">**Mixed Access Levels.**</span></span> <span data-ttu-id="19cfa-184">如果你正在定义一个读 / 写属性，你可以选择指定不同的访问级别也`Get`或`Set`过程中，但不是两者。</span><span class="sxs-lookup"><span data-stu-id="19cfa-184">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="19cfa-185">如果执行此操作时，过程访问级别必须比属性访问级别限制性更强。</span><span class="sxs-lookup"><span data-stu-id="19cfa-185">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="19cfa-186">例如，如果属性声明`Friend`，可以声明`Set`过程`Private`，但不是`Public`。</span><span class="sxs-lookup"><span data-stu-id="19cfa-186">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="19cfa-187">如果你正在定义`ReadOnly`或`WriteOnly`属性、 单个属性过程 (`Get`或`Set`分别) 表示所有属性。</span><span class="sxs-lookup"><span data-stu-id="19cfa-187">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="19cfa-188">不能声明此类过程中，不同的访问级别，因为这会设置属性的两个访问级别。</span><span class="sxs-lookup"><span data-stu-id="19cfa-188">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>  
  
-   <span data-ttu-id="19cfa-189">**返回类型。**</span><span class="sxs-lookup"><span data-stu-id="19cfa-189">**Return Type.**</span></span> <span data-ttu-id="19cfa-190">`Property`语句可以声明其返回的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="19cfa-190">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="19cfa-191">你可以指定任何数据类型或枚举、 结构、 类或接口的名称。</span><span class="sxs-lookup"><span data-stu-id="19cfa-191">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="19cfa-192">如果不指定`returntype`，该属性返回`Object`。</span><span class="sxs-lookup"><span data-stu-id="19cfa-192">If you do not specify `returntype`, the property returns `Object`.</span></span>  
  
-   <span data-ttu-id="19cfa-193">**实现。**</span><span class="sxs-lookup"><span data-stu-id="19cfa-193">**Implementation.**</span></span> <span data-ttu-id="19cfa-194">如果此属性使用`Implements`关键字、 包含的类或结构必须具有`Implements`语句紧靠其`Class`或`Structure`语句。</span><span class="sxs-lookup"><span data-stu-id="19cfa-194">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="19cfa-195">`Implements`语句必须包含在指定每个接口`implementslist`。</span><span class="sxs-lookup"><span data-stu-id="19cfa-195">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="19cfa-196">但是，通过该接口定义的名称`Property`(在`definedname`) 没有为此属性的名称相同 (在`name`)。</span><span class="sxs-lookup"><span data-stu-id="19cfa-196">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="19cfa-197">行为</span><span class="sxs-lookup"><span data-stu-id="19cfa-197">Behavior</span></span>  
  
-   <span data-ttu-id="19cfa-198">**返回从属性过程。**</span><span class="sxs-lookup"><span data-stu-id="19cfa-198">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="19cfa-199">当`Get`或`Set`过程返回到调用代码时，继续执行的语句之后调用它的语句。</span><span class="sxs-lookup"><span data-stu-id="19cfa-199">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>  
  
     <span data-ttu-id="19cfa-200">`Exit Property`和`Return`语句从属性过程会导致立即退出。</span><span class="sxs-lookup"><span data-stu-id="19cfa-200">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="19cfa-201">任意数量的`Exit Property`和`Return`语句可以出现的任何位置在过程中，并可混合`Exit Property`和`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="19cfa-201">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
-   <span data-ttu-id="19cfa-202">**返回值。**</span><span class="sxs-lookup"><span data-stu-id="19cfa-202">**Return Value.**</span></span> <span data-ttu-id="19cfa-203">返回一个介于`Get`过程中，您可以将值分配到属性名称或将其包含在`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="19cfa-203">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="19cfa-204">下面的示例将返回值分配给属性名称`quoteForTheDay`，然后使用`Exit Property`语句以返回。</span><span class="sxs-lookup"><span data-stu-id="19cfa-204">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]  
  
     <span data-ttu-id="19cfa-205">如果你使用`Exit Property`而不将分配到的值`name`、`Get`过程返回该属性的数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="19cfa-205">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>  
  
     <span data-ttu-id="19cfa-206">`Return`语句在同一时间将赋`Get`过程返回值并退出该过程。</span><span class="sxs-lookup"><span data-stu-id="19cfa-206">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="19cfa-207">下面的示例演示了此过程。</span><span class="sxs-lookup"><span data-stu-id="19cfa-207">The following example shows this.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="19cfa-208">示例</span><span class="sxs-lookup"><span data-stu-id="19cfa-208">Example</span></span>  
 <span data-ttu-id="19cfa-209">下面的示例声明一个类中的属性。</span><span class="sxs-lookup"><span data-stu-id="19cfa-209">The following example declares a property in a class.</span></span>  
  
 [!code-vb[VbVbalrStatements#51](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="19cfa-210">请参阅</span><span class="sxs-lookup"><span data-stu-id="19cfa-210">See Also</span></span>  
 [<span data-ttu-id="19cfa-211">自动实现的属性</span><span class="sxs-lookup"><span data-stu-id="19cfa-211">Auto-Implemented Properties</span></span>](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)  
 [<span data-ttu-id="19cfa-212">对象和类</span><span class="sxs-lookup"><span data-stu-id="19cfa-212">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="19cfa-213">Get 语句</span><span class="sxs-lookup"><span data-stu-id="19cfa-213">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="19cfa-214">Set 语句</span><span class="sxs-lookup"><span data-stu-id="19cfa-214">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
 [<span data-ttu-id="19cfa-215">参数列表</span><span class="sxs-lookup"><span data-stu-id="19cfa-215">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [<span data-ttu-id="19cfa-216">默认</span><span class="sxs-lookup"><span data-stu-id="19cfa-216">Default</span></span>](../../../visual-basic/language-reference/modifiers/default.md)
