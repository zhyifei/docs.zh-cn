---
title: Property Statement
ms.date: 05/12/2018
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
ms.openlocfilehash: 3f3ced3f0c441518594820f75243c71fb0c3babd
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
---
# <a name="property-statement"></a><span data-ttu-id="5f120-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="5f120-102">Property Statement</span></span>
<span data-ttu-id="5f120-103">声明的属性，以及用于存储和检索属性的值的属性过程的名称。</span><span class="sxs-lookup"><span data-stu-id="5f120-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f120-104">语法</span><span class="sxs-lookup"><span data-stu-id="5f120-104">Syntax</span></span>  
  
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
  
## <a name="parts"></a><span data-ttu-id="5f120-105">部件</span><span class="sxs-lookup"><span data-stu-id="5f120-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="5f120-106">可选。</span><span class="sxs-lookup"><span data-stu-id="5f120-106">Optional.</span></span> <span data-ttu-id="5f120-107">将应用于此属性的属性列表或`Get`或`Set`过程。</span><span class="sxs-lookup"><span data-stu-id="5f120-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="5f120-108">请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="5f120-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `Default`  
  
     <span data-ttu-id="5f120-109">可选。</span><span class="sxs-lookup"><span data-stu-id="5f120-109">Optional.</span></span> <span data-ttu-id="5f120-110">指定此属性是类或结构定义它的默认属性。</span><span class="sxs-lookup"><span data-stu-id="5f120-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="5f120-111">默认属性必须接受参数并可以设置和检索，而不必指定属性名称。</span><span class="sxs-lookup"><span data-stu-id="5f120-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="5f120-112">如果声明属性作为`Default`，不能使用`Private`的属性上或其属性过程中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="5f120-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="5f120-113">上是可选的`Property`语句和上最多一种`Get`和`Set`语句。</span><span class="sxs-lookup"><span data-stu-id="5f120-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="5f120-114">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="5f120-114">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="5f120-115">Public</span><span class="sxs-lookup"><span data-stu-id="5f120-115">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="5f120-116">Protected</span><span class="sxs-lookup"><span data-stu-id="5f120-116">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="5f120-117">Friend</span><span class="sxs-lookup"><span data-stu-id="5f120-117">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="5f120-118">Private</span><span class="sxs-lookup"><span data-stu-id="5f120-118">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    - [<span data-ttu-id="5f120-119">受保护的友元</span><span class="sxs-lookup"><span data-stu-id="5f120-119">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md) 

    - [<span data-ttu-id="5f120-120">私有受保护</span><span class="sxs-lookup"><span data-stu-id="5f120-120">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)
  
     <span data-ttu-id="5f120-121">请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="5f120-121">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `propertymodifiers`  
  
     <span data-ttu-id="5f120-122">可选。</span><span class="sxs-lookup"><span data-stu-id="5f120-122">Optional.</span></span> <span data-ttu-id="5f120-123">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="5f120-123">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="5f120-124">重载</span><span class="sxs-lookup"><span data-stu-id="5f120-124">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="5f120-125">Overrides</span><span class="sxs-lookup"><span data-stu-id="5f120-125">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="5f120-126">Overridable</span><span class="sxs-lookup"><span data-stu-id="5f120-126">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="5f120-127">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="5f120-127">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="5f120-128">MustOverride</span><span class="sxs-lookup"><span data-stu-id="5f120-128">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="5f120-129">可选。</span><span class="sxs-lookup"><span data-stu-id="5f120-129">Optional.</span></span> <span data-ttu-id="5f120-130">请参阅[共享](../../../visual-basic/language-reference/modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="5f120-130">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="5f120-131">可选。</span><span class="sxs-lookup"><span data-stu-id="5f120-131">Optional.</span></span> <span data-ttu-id="5f120-132">请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。</span><span class="sxs-lookup"><span data-stu-id="5f120-132">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="5f120-133">可选。</span><span class="sxs-lookup"><span data-stu-id="5f120-133">Optional.</span></span> <span data-ttu-id="5f120-134">请参阅[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="5f120-134">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WriteOnly`  
  
     <span data-ttu-id="5f120-135">可选。</span><span class="sxs-lookup"><span data-stu-id="5f120-135">Optional.</span></span> <span data-ttu-id="5f120-136">请参阅[WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)。</span><span class="sxs-lookup"><span data-stu-id="5f120-136">See [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="5f120-137">可选。</span><span class="sxs-lookup"><span data-stu-id="5f120-137">Optional.</span></span> <span data-ttu-id="5f120-138">请参阅[迭代器](../../../visual-basic/language-reference/modifiers/iterator.md)。</span><span class="sxs-lookup"><span data-stu-id="5f120-138">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="5f120-139">必须的。</span><span class="sxs-lookup"><span data-stu-id="5f120-139">Required.</span></span> <span data-ttu-id="5f120-140">属性的名称。</span><span class="sxs-lookup"><span data-stu-id="5f120-140">Name of the property.</span></span> <span data-ttu-id="5f120-141">请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="5f120-141">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="5f120-142">可选。</span><span class="sxs-lookup"><span data-stu-id="5f120-142">Optional.</span></span> <span data-ttu-id="5f120-143">表示此属性的参数和可能具有的其他参数的本地变量名的列表`Set`过程。</span><span class="sxs-lookup"><span data-stu-id="5f120-143">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="5f120-144">请参阅[参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)。</span><span class="sxs-lookup"><span data-stu-id="5f120-144">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="5f120-145">如果存在`Option``Strict`是`On`。</span><span class="sxs-lookup"><span data-stu-id="5f120-145">Required if `Option``Strict` is `On`.</span></span> <span data-ttu-id="5f120-146">返回此属性的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="5f120-146">Data type of the value returned by this property.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="5f120-147">可选。</span><span class="sxs-lookup"><span data-stu-id="5f120-147">Optional.</span></span> <span data-ttu-id="5f120-148">指示此属性实现一个或多个属性，此属性包含的类或结构实现接口中定义的每个组。</span><span class="sxs-lookup"><span data-stu-id="5f120-148">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="5f120-149">请参阅[实现语句](../../../visual-basic/language-reference/statements/implements-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="5f120-149">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="5f120-150">如果提供 `Implements`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="5f120-150">Required if `Implements` is supplied.</span></span> <span data-ttu-id="5f120-151">正在实现的属性的列表。</span><span class="sxs-lookup"><span data-stu-id="5f120-151">List of properties being implemented.</span></span>  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     <span data-ttu-id="5f120-152">每个 `implementedproperty` 都具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="5f120-152">Each `implementedproperty` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="5f120-153">部件</span><span class="sxs-lookup"><span data-stu-id="5f120-153">Part</span></span>|<span data-ttu-id="5f120-154">描述</span><span class="sxs-lookup"><span data-stu-id="5f120-154">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="5f120-155">必须的。</span><span class="sxs-lookup"><span data-stu-id="5f120-155">Required.</span></span> <span data-ttu-id="5f120-156">包含此属性实现的接口名称的类或结构。</span><span class="sxs-lookup"><span data-stu-id="5f120-156">Name of an interface implemented by this property's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="5f120-157">必须的。</span><span class="sxs-lookup"><span data-stu-id="5f120-157">Required.</span></span> <span data-ttu-id="5f120-158">中定义的属性的名称`interface`。</span><span class="sxs-lookup"><span data-stu-id="5f120-158">Name by which the property is defined in `interface`.</span></span>|  
  
-   `Get`  
  
     <span data-ttu-id="5f120-159">可选。</span><span class="sxs-lookup"><span data-stu-id="5f120-159">Optional.</span></span> <span data-ttu-id="5f120-160">所需属性如果标记`WriteOnly`。</span><span class="sxs-lookup"><span data-stu-id="5f120-160">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="5f120-161">启动`Get`用于返回属性的值的属性过程。</span><span class="sxs-lookup"><span data-stu-id="5f120-161">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  
  
-   `statements`  
  
     <span data-ttu-id="5f120-162">可选。</span><span class="sxs-lookup"><span data-stu-id="5f120-162">Optional.</span></span> <span data-ttu-id="5f120-163">要在中运行的语句块`Get`或`Set`过程。</span><span class="sxs-lookup"><span data-stu-id="5f120-163">Block of statements to run within the `Get` or `Set` procedure.</span></span>  
  
-   `End Get`  
  
     <span data-ttu-id="5f120-164">终止`Get`属性过程。</span><span class="sxs-lookup"><span data-stu-id="5f120-164">Terminates the `Get` property procedure.</span></span>  
  
-   `Set`  
  
     <span data-ttu-id="5f120-165">可选。</span><span class="sxs-lookup"><span data-stu-id="5f120-165">Optional.</span></span> <span data-ttu-id="5f120-166">所需属性如果标记`ReadOnly`。</span><span class="sxs-lookup"><span data-stu-id="5f120-166">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="5f120-167">启动`Set`用于存储属性的值的属性过程。</span><span class="sxs-lookup"><span data-stu-id="5f120-167">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  
  
-   `End Set`  
  
     <span data-ttu-id="5f120-168">终止`Set`属性过程。</span><span class="sxs-lookup"><span data-stu-id="5f120-168">Terminates the `Set` property procedure.</span></span>  
  
-   `End Property`  
  
     <span data-ttu-id="5f120-169">终止此属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5f120-169">Terminates the definition of this property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f120-170">备注</span><span class="sxs-lookup"><span data-stu-id="5f120-170">Remarks</span></span>  
 <span data-ttu-id="5f120-171">`Property`语句会引入属性声明。</span><span class="sxs-lookup"><span data-stu-id="5f120-171">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="5f120-172">属性可以具有`Get`过程 （只读），`Set`过程 （只写） 或二者 （读写）。</span><span class="sxs-lookup"><span data-stu-id="5f120-172">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="5f120-173">可以省略`Get`和`Set`过程时使用一个自动实现的属性。</span><span class="sxs-lookup"><span data-stu-id="5f120-173">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="5f120-174">有关详细信息，请参阅[自动实现的属性](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="5f120-174">For more information, see [Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="5f120-175">你可以使用`Property`只能在类级别。</span><span class="sxs-lookup"><span data-stu-id="5f120-175">You can use `Property` only at class level.</span></span> <span data-ttu-id="5f120-176">这意味着*声明上下文*属性必须为类、 结构、 模块或接口，并且不能是源文件、 命名空间、 过程中或块。</span><span class="sxs-lookup"><span data-stu-id="5f120-176">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="5f120-177">有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="5f120-177">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="5f120-178">默认情况下，属性使用公共访问权限。</span><span class="sxs-lookup"><span data-stu-id="5f120-178">By default, properties use public access.</span></span> <span data-ttu-id="5f120-179">可以调整使用访问修饰符的属性的访问级别`Property`语句，然后你可以选择性地调整其一个属性过程限制性更强的访问级别。</span><span class="sxs-lookup"><span data-stu-id="5f120-179">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>  
  
 <span data-ttu-id="5f120-180">Visual Basic 将传递到参数`Set`属性分配期间的过程。</span><span class="sxs-lookup"><span data-stu-id="5f120-180">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="5f120-181">如果未提供的参数`Set`，集成的开发环境 (IDE) 使用名为的隐式参数`value`。</span><span class="sxs-lookup"><span data-stu-id="5f120-181">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="5f120-182">此参数包含要分配给属性的值。</span><span class="sxs-lookup"><span data-stu-id="5f120-182">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="5f120-183">通常将此值存储在专用的本地变量，并将其返回每当`Get`调用过程。</span><span class="sxs-lookup"><span data-stu-id="5f120-183">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="5f120-184">规则</span><span class="sxs-lookup"><span data-stu-id="5f120-184">Rules</span></span>  
  
-   <span data-ttu-id="5f120-185">**混合的访问级别。**</span><span class="sxs-lookup"><span data-stu-id="5f120-185">**Mixed Access Levels.**</span></span> <span data-ttu-id="5f120-186">如果你正在定义一个读 / 写属性，你可以选择指定不同的访问级别也`Get`或`Set`过程中，但不是两者。</span><span class="sxs-lookup"><span data-stu-id="5f120-186">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="5f120-187">如果执行此操作时，过程访问级别必须比属性访问级别限制性更强。</span><span class="sxs-lookup"><span data-stu-id="5f120-187">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="5f120-188">例如，如果属性声明`Friend`，可以声明`Set`过程`Private`，但不是`Public`。</span><span class="sxs-lookup"><span data-stu-id="5f120-188">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="5f120-189">如果你正在定义`ReadOnly`或`WriteOnly`属性、 单个属性过程 (`Get`或`Set`分别) 表示所有属性。</span><span class="sxs-lookup"><span data-stu-id="5f120-189">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="5f120-190">不能声明此类过程中，不同的访问级别，因为这会设置属性的两个访问级别。</span><span class="sxs-lookup"><span data-stu-id="5f120-190">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>  
  
-   <span data-ttu-id="5f120-191">**返回类型。**</span><span class="sxs-lookup"><span data-stu-id="5f120-191">**Return Type.**</span></span> <span data-ttu-id="5f120-192">`Property`语句可以声明其返回的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="5f120-192">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="5f120-193">你可以指定任何数据类型或枚举、 结构、 类或接口的名称。</span><span class="sxs-lookup"><span data-stu-id="5f120-193">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="5f120-194">如果不指定`returntype`，该属性返回`Object`。</span><span class="sxs-lookup"><span data-stu-id="5f120-194">If you do not specify `returntype`, the property returns `Object`.</span></span>  
  
-   <span data-ttu-id="5f120-195">**实现。**</span><span class="sxs-lookup"><span data-stu-id="5f120-195">**Implementation.**</span></span> <span data-ttu-id="5f120-196">如果此属性使用`Implements`关键字、 包含的类或结构必须具有`Implements`语句紧靠其`Class`或`Structure`语句。</span><span class="sxs-lookup"><span data-stu-id="5f120-196">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="5f120-197">`Implements`语句必须包含在指定每个接口`implementslist`。</span><span class="sxs-lookup"><span data-stu-id="5f120-197">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="5f120-198">但是，通过该接口定义的名称`Property`(在`definedname`) 没有为此属性的名称相同 (在`name`)。</span><span class="sxs-lookup"><span data-stu-id="5f120-198">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="5f120-199">行为</span><span class="sxs-lookup"><span data-stu-id="5f120-199">Behavior</span></span>  
  
-   <span data-ttu-id="5f120-200">**返回从属性过程。**</span><span class="sxs-lookup"><span data-stu-id="5f120-200">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="5f120-201">当`Get`或`Set`过程返回到调用代码时，继续执行的语句之后调用它的语句。</span><span class="sxs-lookup"><span data-stu-id="5f120-201">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>  
  
     <span data-ttu-id="5f120-202">`Exit Property`和`Return`语句从属性过程会导致立即退出。</span><span class="sxs-lookup"><span data-stu-id="5f120-202">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="5f120-203">任意数量的`Exit Property`和`Return`语句可以出现的任何位置在过程中，并可混合`Exit Property`和`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="5f120-203">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
-   <span data-ttu-id="5f120-204">**返回值。**</span><span class="sxs-lookup"><span data-stu-id="5f120-204">**Return Value.**</span></span> <span data-ttu-id="5f120-205">返回一个介于`Get`过程中，您可以将值分配到属性名称或将其包含在`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="5f120-205">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="5f120-206">下面的示例将返回值分配给属性名称`quoteForTheDay`，然后使用`Exit Property`语句以返回。</span><span class="sxs-lookup"><span data-stu-id="5f120-206">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]  
  
     <span data-ttu-id="5f120-207">如果你使用`Exit Property`而不将分配到的值`name`、`Get`过程返回该属性的数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="5f120-207">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>  
  
     <span data-ttu-id="5f120-208">`Return`语句在同一时间将赋`Get`过程返回值并退出该过程。</span><span class="sxs-lookup"><span data-stu-id="5f120-208">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="5f120-209">下面的示例演示了此过程。</span><span class="sxs-lookup"><span data-stu-id="5f120-209">The following example shows this.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="5f120-210">示例</span><span class="sxs-lookup"><span data-stu-id="5f120-210">Example</span></span>  
 <span data-ttu-id="5f120-211">下面的示例声明一个类中的属性。</span><span class="sxs-lookup"><span data-stu-id="5f120-211">The following example declares a property in a class.</span></span>  
  
 [!code-vb[VbVbalrStatements#51](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5f120-212">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f120-212">See Also</span></span>  
 [<span data-ttu-id="5f120-213">自动实现的属性</span><span class="sxs-lookup"><span data-stu-id="5f120-213">Auto-Implemented Properties</span></span>](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)  
 [<span data-ttu-id="5f120-214">对象和类</span><span class="sxs-lookup"><span data-stu-id="5f120-214">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="5f120-215">Get 语句</span><span class="sxs-lookup"><span data-stu-id="5f120-215">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="5f120-216">Set 语句</span><span class="sxs-lookup"><span data-stu-id="5f120-216">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
 [<span data-ttu-id="5f120-217">参数列表</span><span class="sxs-lookup"><span data-stu-id="5f120-217">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [<span data-ttu-id="5f120-218">默认</span><span class="sxs-lookup"><span data-stu-id="5f120-218">Default</span></span>](../../../visual-basic/language-reference/modifiers/default.md)
