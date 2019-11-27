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
ms.openlocfilehash: 80bce2442d96ecb9c548a88c8e5ee44c6258473b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346761"
---
# <a name="property-statement"></a><span data-ttu-id="f6ee2-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="f6ee2-102">Property Statement</span></span>

<span data-ttu-id="f6ee2-103">声明属性的名称，以及用于存储和检索属性值的属性过程。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>

## <a name="syntax"></a><span data-ttu-id="f6ee2-104">语法</span><span class="sxs-lookup"><span data-stu-id="f6ee2-104">Syntax</span></span>

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

## <a name="parts"></a><span data-ttu-id="f6ee2-105">部件</span><span class="sxs-lookup"><span data-stu-id="f6ee2-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="f6ee2-106">可选。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-106">Optional.</span></span> <span data-ttu-id="f6ee2-107">应用于此属性或 `Get` 或 `Set` 过程的特性的列表。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="f6ee2-108">请参阅[特性列表](attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-108">See [Attribute List](attribute-list.md).</span></span>

- `Default`

  <span data-ttu-id="f6ee2-109">可选。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-109">Optional.</span></span> <span data-ttu-id="f6ee2-110">指定此属性是在其上定义该属性的类或结构的默认属性。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="f6ee2-111">默认属性必须接受参数，并且可以在不指定属性名称的情况下进行设置和检索。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="f6ee2-112">如果将属性声明为 `Default`，则不能对属性或它的任何一个属性过程使用 `Private`。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>

- `accessmodifier`

  <span data-ttu-id="f6ee2-113">在 `Property` 语句上以及最多一个 `Get` 和 `Set` 语句上是可选的。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="f6ee2-114">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="f6ee2-114">Can be one of the following:</span></span>

  - [<span data-ttu-id="f6ee2-115">Public</span><span class="sxs-lookup"><span data-stu-id="f6ee2-115">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="f6ee2-116">Protected</span><span class="sxs-lookup"><span data-stu-id="f6ee2-116">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="f6ee2-117">Friend</span><span class="sxs-lookup"><span data-stu-id="f6ee2-117">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="f6ee2-118">Private</span><span class="sxs-lookup"><span data-stu-id="f6ee2-118">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="f6ee2-119">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="f6ee2-119">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="f6ee2-120">Private Protected</span><span class="sxs-lookup"><span data-stu-id="f6ee2-120">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="f6ee2-121">请参阅 [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-121">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `propertymodifiers`

  <span data-ttu-id="f6ee2-122">可选。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-122">Optional.</span></span> <span data-ttu-id="f6ee2-123">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="f6ee2-123">Can be one of the following:</span></span>

  - [<span data-ttu-id="f6ee2-124">Overloads</span><span class="sxs-lookup"><span data-stu-id="f6ee2-124">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="f6ee2-125">Overrides</span><span class="sxs-lookup"><span data-stu-id="f6ee2-125">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="f6ee2-126">Overrides</span><span class="sxs-lookup"><span data-stu-id="f6ee2-126">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="f6ee2-127">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="f6ee2-127">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="f6ee2-128">MyBase</span><span class="sxs-lookup"><span data-stu-id="f6ee2-128">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="f6ee2-129">可选。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-129">Optional.</span></span> <span data-ttu-id="f6ee2-130">请参阅[共享](../modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-130">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="f6ee2-131">可选。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-131">Optional.</span></span> <span data-ttu-id="f6ee2-132">请参阅[阴影](../modifiers/shadows.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-132">See [Shadows](../modifiers/shadows.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="f6ee2-133">可选。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-133">Optional.</span></span> <span data-ttu-id="f6ee2-134">请参阅[ReadOnly](../modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-134">See [ReadOnly](../modifiers/readonly.md).</span></span>

- `WriteOnly`

  <span data-ttu-id="f6ee2-135">可选。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-135">Optional.</span></span> <span data-ttu-id="f6ee2-136">请参阅[WriteOnly](../modifiers/writeonly.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-136">See [WriteOnly](../modifiers/writeonly.md).</span></span>

- `Iterator`

  <span data-ttu-id="f6ee2-137">可选。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-137">Optional.</span></span> <span data-ttu-id="f6ee2-138">请参阅[迭代器](../modifiers/iterator.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-138">See [Iterator](../modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="f6ee2-139">必需。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-139">Required.</span></span> <span data-ttu-id="f6ee2-140">属性的名称。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-140">Name of the property.</span></span> <span data-ttu-id="f6ee2-141">请参阅 [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-141">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `parameterlist`

  <span data-ttu-id="f6ee2-142">可选。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-142">Optional.</span></span> <span data-ttu-id="f6ee2-143">表示此属性的参数以及 `Set` 过程可能的其他参数的局部变量名称列表。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-143">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="f6ee2-144">请参阅[参数列表](parameter-list.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-144">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="f6ee2-145">如果 `Option Strict` `On`，则为必需。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-145">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="f6ee2-146">此属性返回的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-146">Data type of the value returned by this property.</span></span>

- `Implements`

  <span data-ttu-id="f6ee2-147">可选。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-147">Optional.</span></span> <span data-ttu-id="f6ee2-148">指示此属性实现一个或多个属性，每个属性都是由该属性的包含类或结构实现的接口中定义的。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-148">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="f6ee2-149">请参阅[Implements 语句](implements-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-149">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="f6ee2-150">如果提供 `Implements`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-150">Required if `Implements` is supplied.</span></span> <span data-ttu-id="f6ee2-151">要实现的属性列表。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-151">List of properties being implemented.</span></span>

  `implementedproperty [ , implementedproperty ... ]`

  <span data-ttu-id="f6ee2-152">每个 `implementedproperty` 都具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="f6ee2-152">Each `implementedproperty` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="f6ee2-153">部件</span><span class="sxs-lookup"><span data-stu-id="f6ee2-153">Part</span></span>|<span data-ttu-id="f6ee2-154">说明</span><span class="sxs-lookup"><span data-stu-id="f6ee2-154">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="f6ee2-155">必需。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-155">Required.</span></span> <span data-ttu-id="f6ee2-156">此属性的包含类或结构实现的接口的名称。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-156">Name of an interface implemented by this property's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="f6ee2-157">必需。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-157">Required.</span></span> <span data-ttu-id="f6ee2-158">用于在 `interface`中定义属性的名称。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-158">Name by which the property is defined in `interface`.</span></span>|

- `Get`

  <span data-ttu-id="f6ee2-159">可选。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-159">Optional.</span></span> <span data-ttu-id="f6ee2-160">如果将属性标记 `ReadOnly`，则为必需。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-160">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="f6ee2-161">启动 `Get` 属性过程，该过程用于返回属性的值。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-161">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  <span data-ttu-id="f6ee2-162">`Get` 语句不与[自动实现的属性](../../programming-guide/language-features/procedures/auto-implemented-properties.md)一起使用。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-162">The `Get` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `statements`

  <span data-ttu-id="f6ee2-163">可选。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-163">Optional.</span></span> <span data-ttu-id="f6ee2-164">要在 `Get` 或 `Set` 过程中运行的语句块。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-164">Block of statements to run within the `Get` or `Set` procedure.</span></span>

- `End Get`

  <span data-ttu-id="f6ee2-165">终止 `Get` 属性过程。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-165">Terminates the `Get` property procedure.</span></span>

- `Set`

  <span data-ttu-id="f6ee2-166">可选。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-166">Optional.</span></span> <span data-ttu-id="f6ee2-167">如果将属性标记 `WriteOnly`，则为必需。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-167">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="f6ee2-168">启动 `Set` 属性过程，该过程用于存储属性的值。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-168">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  <span data-ttu-id="f6ee2-169">`Set` 语句不与[自动实现的属性](../../programming-guide/language-features/procedures/auto-implemented-properties.md)一起使用。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-169">The `Set` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `End Set`

  <span data-ttu-id="f6ee2-170">终止 `Set` 属性过程。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-170">Terminates the `Set` property procedure.</span></span>

- `End Property`

  <span data-ttu-id="f6ee2-171">终止此属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-171">Terminates the definition of this property.</span></span>

## <a name="remarks"></a><span data-ttu-id="f6ee2-172">备注</span><span class="sxs-lookup"><span data-stu-id="f6ee2-172">Remarks</span></span>

<span data-ttu-id="f6ee2-173">`Property` 语句引入属性的声明。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-173">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="f6ee2-174">属性可以有 `Get` 过程（只读）、`Set` 过程（只写）或两者（读写）。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-174">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="f6ee2-175">使用自动实现的属性时，可以省略 `Get` 和 `Set` 过程。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-175">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="f6ee2-176">有关详细信息，请参阅[自动实现的属性](../../programming-guide/language-features/procedures/auto-implemented-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-176">For more information, see [Auto-Implemented Properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

<span data-ttu-id="f6ee2-177">只能在类级别使用 `Property`。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-177">You can use `Property` only at class level.</span></span> <span data-ttu-id="f6ee2-178">这意味着属性的*声明上下文*必须是类、结构、模块或接口，不能是源文件、命名空间、过程或块。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-178">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="f6ee2-179">有关详细信息，请参阅[声明上下文和默认访问级别](declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-179">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="f6ee2-180">默认情况下，属性使用公共访问。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-180">By default, properties use public access.</span></span> <span data-ttu-id="f6ee2-181">您可以使用 `Property` 语句的访问修饰符调整属性的访问级别，还可以根据需要将其属性过程之一调整到限制性更强的访问级别。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-181">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>

<span data-ttu-id="f6ee2-182">Visual Basic 在属性赋值期间将参数传递给 `Set` 过程。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-182">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="f6ee2-183">如果没有为 `Set`提供参数，集成开发环境（IDE）将使用名为 `value`的隐式参数。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-183">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="f6ee2-184">此参数保存要赋给属性的值。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-184">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="f6ee2-185">通常将此值存储在私有本地变量中，并在调用 `Get` 过程时返回此值。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-185">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>

## <a name="rules"></a><span data-ttu-id="f6ee2-186">规则</span><span class="sxs-lookup"><span data-stu-id="f6ee2-186">Rules</span></span>

- <span data-ttu-id="f6ee2-187">**混合访问级别。**</span><span class="sxs-lookup"><span data-stu-id="f6ee2-187">**Mixed Access Levels.**</span></span> <span data-ttu-id="f6ee2-188">如果要定义读写属性，则可以选择为 `Get` 或 `Set` 过程指定不同的访问级别，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-188">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="f6ee2-189">如果执行此操作，则过程访问级别必须比属性的访问级别更严格。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-189">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="f6ee2-190">例如，如果属性已 `Friend`声明，则可以将 `Set` 过程声明 `Private`但不 `Public`。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-190">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>

  <span data-ttu-id="f6ee2-191">如果要定义 `ReadOnly` 或 `WriteOnly` 属性，则单个属性过程（分别为`Get` 或 `Set`）表示所有属性。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-191">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="f6ee2-192">不能为此类过程声明不同的访问级别，因为这会为属性设置两个访问级别。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-192">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>

- <span data-ttu-id="f6ee2-193">**返回类型。**</span><span class="sxs-lookup"><span data-stu-id="f6ee2-193">**Return Type.**</span></span> <span data-ttu-id="f6ee2-194">`Property` 语句可以声明其返回的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-194">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="f6ee2-195">您可以指定任何数据类型或枚举、结构、类或接口的名称。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-195">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

  <span data-ttu-id="f6ee2-196">如果不指定 `returntype`，属性将返回 `Object`。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-196">If you do not specify `returntype`, the property returns `Object`.</span></span>

- <span data-ttu-id="f6ee2-197">**部署.**</span><span class="sxs-lookup"><span data-stu-id="f6ee2-197">**Implementation.**</span></span> <span data-ttu-id="f6ee2-198">如果此属性使用 `Implements` 关键字，则包含类或结构必须紧跟在其 `Class` 或 `Structure` 语句后面的 `Implements` 语句。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-198">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="f6ee2-199">`Implements` 语句必须包括 `implementslist`中指定的每个接口。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-199">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="f6ee2-200">但是，接口定义 `Property` （在 `definedname`中）的名称不必与此属性的名称相同（在 `name`中）。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-200">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>

## <a name="behavior"></a><span data-ttu-id="f6ee2-201">行为</span><span class="sxs-lookup"><span data-stu-id="f6ee2-201">Behavior</span></span>

- <span data-ttu-id="f6ee2-202">**从属性过程返回。**</span><span class="sxs-lookup"><span data-stu-id="f6ee2-202">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="f6ee2-203">当 `Get` 或 `Set` 过程返回到调用代码时，执行将继续执行调用它的语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-203">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>

  <span data-ttu-id="f6ee2-204">`Exit Property` 和 `Return` 语句导致直接从属性过程退出。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-204">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="f6ee2-205">任意数量的 `Exit Property` 和 `Return` 语句可以出现在过程中的任何位置，并且可以混合 `Exit Property` 和 `Return` 语句。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-205">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>

- <span data-ttu-id="f6ee2-206">**返回值。**</span><span class="sxs-lookup"><span data-stu-id="f6ee2-206">**Return Value.**</span></span> <span data-ttu-id="f6ee2-207">若要从 `Get` 过程返回值，可将值分配给属性名称或将其包含在 `Return` 语句中。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-207">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="f6ee2-208">下面的示例将返回值分配给属性名称 `quoteForTheDay`，然后使用 `Exit Property` 语句返回。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-208">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  <span data-ttu-id="f6ee2-209">如果使用 `Exit Property` 但未向 `name`赋值，`Get` 过程将返回属性数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-209">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>

  <span data-ttu-id="f6ee2-210">`Return` 语句同时分配 `Get` 过程返回值并退出该过程。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-210">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="f6ee2-211">下面的示例演示了这一点。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-211">The following example shows this.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a><span data-ttu-id="f6ee2-212">示例</span><span class="sxs-lookup"><span data-stu-id="f6ee2-212">Example</span></span>

<span data-ttu-id="f6ee2-213">下面的示例声明类中的一个属性。</span><span class="sxs-lookup"><span data-stu-id="f6ee2-213">The following example declares a property in a class.</span></span>

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="f6ee2-214">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6ee2-214">See also</span></span>

- [<span data-ttu-id="f6ee2-215">自动实现的属性</span><span class="sxs-lookup"><span data-stu-id="f6ee2-215">Auto-Implemented Properties</span></span>](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [<span data-ttu-id="f6ee2-216">对象和类</span><span class="sxs-lookup"><span data-stu-id="f6ee2-216">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="f6ee2-217">Get 语句</span><span class="sxs-lookup"><span data-stu-id="f6ee2-217">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="f6ee2-218">Set 语句</span><span class="sxs-lookup"><span data-stu-id="f6ee2-218">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="f6ee2-219">参数列表</span><span class="sxs-lookup"><span data-stu-id="f6ee2-219">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="f6ee2-220">Default</span><span class="sxs-lookup"><span data-stu-id="f6ee2-220">Default</span></span>](../modifiers/default.md)
