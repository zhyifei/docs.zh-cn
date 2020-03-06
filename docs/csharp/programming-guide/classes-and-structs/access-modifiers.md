---
title: 访问修饰符 - C# 编程指南
ms.date: 03/08/2020
helpviewer_keywords:
- C# Language, access modifiers
- access modifiers [C#], about
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
ms.openlocfilehash: 749d53344a2518966cfa5d937069ba73dfd6be8f
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628223"
---
# <a name="access-modifiers-c-programming-guide"></a><span data-ttu-id="cb1f6-102">访问修饰符（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="cb1f6-102">Access Modifiers (C# Programming Guide)</span></span>

<span data-ttu-id="cb1f6-103">所有类型和类型成员都具有可访问性级别。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-103">All types and type members have an accessibility level.</span></span> <span data-ttu-id="cb1f6-104">该级别可以控制是否可以从你的程序集或其他程序集中的其他代码中使用它们。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-104">The accessibility level controls whether they can be used from other code in your assembly or other assemblies.</span></span> <span data-ttu-id="cb1f6-105">可以使用以下访问修饰符在进行声明时指定类型或成员的可访问性：</span><span class="sxs-lookup"><span data-stu-id="cb1f6-105">Use the following access modifiers to specify the accessibility of a type or member when you declare it:</span></span>

- <span data-ttu-id="cb1f6-106">[public](../../language-reference/keywords/public.md)：同一程序集中的任何其他代码或引用该程序集的其他程序集都可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-106">[public](../../language-reference/keywords/public.md): The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>
- <span data-ttu-id="cb1f6-107">[private](../../language-reference/keywords/private.md)：只有同一 `class` 或 `struct` 中的代码可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-107">[private](../../language-reference/keywords/private.md): The type or member can be accessed only by code in the same `class` or `struct`.</span></span>
- <span data-ttu-id="cb1f6-108">[protected](../../language-reference/keywords/protected.md)：只有同一 `class` 或者从该 `class` 派生的 `class` 中的代码可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-108">[protected](../../language-reference/keywords/protected.md): The type or member can be accessed only by code in the same `class`, or in a `class` that is derived from that `class`.</span></span>
- <span data-ttu-id="cb1f6-109">[internal](../../language-reference/keywords/internal.md)：同一程序集中的任何代码都可以访问该类型或成员，但其他程序集中的代码不可以。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-109">[internal](../../language-reference/keywords/internal.md): The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>
- <span data-ttu-id="cb1f6-110">[protected internal](../../language-reference/keywords/protected-internal.md)：该类型或成员可由对其进行声明的程序集或另一程序集中的派生 `class` 中的任何代码访问。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-110">[protected internal](../../language-reference/keywords/protected-internal.md): The type or member can be accessed by any code in the assembly in which it's declared, or from within a derived `class` in another assembly.</span></span>
- <span data-ttu-id="cb1f6-111">[private protected](../../language-reference/keywords/private-protected.md)：只有在其声明程序集内，通过相同 `class` 中的代码或派生自该 `class` 的类型，才能访问类型或成员。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-111">[private protected](../../language-reference/keywords/private-protected.md): The type or member can be accessed only within its declaring assembly, by code in the same `class` or in a type that is derived from that `class`.</span></span>

<span data-ttu-id="cb1f6-112">下面的示例演示如何在类型和成员上指定访问修饰符：</span><span class="sxs-lookup"><span data-stu-id="cb1f6-112">The following examples demonstrate how to specify access modifiers on a type and member:</span></span>

[!code-csharp[PublicAccess](~/samples/snippets/csharp/objectoriented/accessmodifiers.cs#PublicAccess)]

<span data-ttu-id="cb1f6-113">不是所有访问修饰符都可以在所有上下文中由所有类型或成员使用。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-113">Not all access modifiers are valid for all types or members in all contexts.</span></span> <span data-ttu-id="cb1f6-114">在某些情况下，类型成员的可访问性受到其包含类型的可访问性的限制。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-114">In some cases, the accessibility of a type member is constrained by the accessibility of its containing type.</span></span>

## <a name="class-and-struct-accessibility"></a><span data-ttu-id="cb1f6-115">类和结构可访问性</span><span class="sxs-lookup"><span data-stu-id="cb1f6-115">Class and struct accessibility</span></span>  

<span data-ttu-id="cb1f6-116">直接在命名空间中声明的类和结构（即，没有嵌套在其他类或结构中的类和结构）可以为 `public` 或 `internal`。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-116">Classes and structs declared directly within a namespace (in other words, that aren't nested within other classes or structs) can be either `public` or `internal`.</span></span> <span data-ttu-id="cb1f6-117">如果未指定任何访问修饰符，则默认设置为 `Internal`。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-117">`Internal` is the default if no access modifier is specified.</span></span>  

<span data-ttu-id="cb1f6-118">结构成员（包括嵌套的类和结构）可以声明为 `public`、`internal` 或 `private`。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-118">Struct members, including nested classes and structs, can be declared `public`, `internal`, or `private`.</span></span> <span data-ttu-id="cb1f6-119">类成员（包括嵌套的类和结构）可以声明为 `public`、`protected internal`、`protected`、`internal`、`private protected` 或 `private`。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-119">Class members, including nested classes and structs, can be `public`, `protected internal`, `protected`, `internal`, `private protected`, or `private`.</span></span> <span data-ttu-id="cb1f6-120">默认情况下，类成员和结构成员（包括嵌套的类和结构）的访问级别为 `private`。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-120">Class and struct members,  including nested classes and structs, have `private` access by default.</span></span> <span data-ttu-id="cb1f6-121">不能从包含类型的外部访问私有嵌套类型。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-121">Private nested types aren't accessible from outside the containing type.</span></span>

<span data-ttu-id="cb1f6-122">派生类不能具有高于其基类型的可访问性。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-122">Derived classes can't have greater accessibility than their base types.</span></span> <span data-ttu-id="cb1f6-123">不能声明派生自内部类 `A` 的公共类 `B`。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-123">You can't declare a public class `B` that derives from an internal class `A`.</span></span> <span data-ttu-id="cb1f6-124">如果允许这样，则它将具有使 `A` 公开的效果，因为可从派生类访问 `A` 的所有 `protected` 或 `internal` 成员。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-124">If allowed, it would have the effect of making `A` public, because all `protected` or `internal` members of `A` are accessible from the derived class.</span></span>

<span data-ttu-id="cb1f6-125">可以通过使用 `InternalsVisibleToAttribute` 启用特定的其他程序集访问内部类型。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-125">You can enable specific other assemblies to access your internal types by using the `InternalsVisibleToAttribute`.</span></span> <span data-ttu-id="cb1f6-126">有关详细信息，请参阅[友元程序集](../../../standard/assembly/friend.md)。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-126">For more information, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>

## <a name="class-and-struct-member-accessibility"></a><span data-ttu-id="cb1f6-127">类和结构成员可访问性</span><span class="sxs-lookup"><span data-stu-id="cb1f6-127">Class and struct member accessibility</span></span>  

<span data-ttu-id="cb1f6-128">可以使用六种访问类型中的任意一种声明类成员（包括嵌套的类和结构）。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-128">Class members (including nested classes and structs) can be declared with any of the six types of access.</span></span> <span data-ttu-id="cb1f6-129">结构成员无法声明为 `protected`、`protected internal` 或 `private protected`，因为结构不支持继承。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-129">Struct members can't be declared as `protected`, `protected internal`, or `private protected` because structs don't support inheritance.</span></span>

<span data-ttu-id="cb1f6-130">通常情况下，成员的可访问性不大于包含该成员的类型的可访问性。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-130">Normally, the accessibility of a member isn't greater than the accessibility of the type that contains it.</span></span> <span data-ttu-id="cb1f6-131">但是，如果内部类的 `public` 成员实现了接口方法或替代了在公共基类中定义的虚拟方法，则可从该程序集的外部访问该成员。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-131">However, a `public` member of an internal class might be accessible from outside the assembly if the member implements interface methods or overrides virtual methods that are defined in a public base class.</span></span>

<span data-ttu-id="cb1f6-132">为字段、属性或事件的任何成员的类型必须至少与该成员本身具有相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-132">The type of any member field, property, or event must be at least as accessible as the member itself.</span></span> <span data-ttu-id="cb1f6-133">同样，任何方法、索引器或委托的返回类型和参数类型必须至少与该成员本身具有相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-133">Similarly, the return type and the parameter types of any method, indexer, or delegate must be at least as accessible as the member itself.</span></span> <span data-ttu-id="cb1f6-134">例如，除非 `C` 也是 `public`，否则不能具有返回类 `C` 的 `public` 方法 `M`。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-134">For example, you can't have a `public` method `M` that returns a class `C` unless `C` is also `public`.</span></span> <span data-ttu-id="cb1f6-135">同样，如果 `A` 声明为 `private`，则不能具有类型 `A` 的 `protected` 属性。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-135">Likewise, you can't have a `protected` property of type `A` if `A` is declared as `private`.</span></span>

<span data-ttu-id="cb1f6-136">用户定义的运算符始终必须声明为 `public` 和 `static`。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-136">User-defined operators must always be declared as `public` and `static`.</span></span> <span data-ttu-id="cb1f6-137">有关详细信息，请参阅[运算符重载](../../language-reference/operators/operator-overloading.md)。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-137">For more information, see [Operator overloading](../../language-reference/operators/operator-overloading.md).</span></span>

<span data-ttu-id="cb1f6-138">终结器不能具有可访问性修饰符。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-138">Finalizers can't have accessibility modifiers.</span></span>

<span data-ttu-id="cb1f6-139">若要设置 `class` 或 `struct` 成员的访问级别，请向成员声明添加适当的关键字，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-139">To set the access level for a `class` or `struct` member, add the appropriate keyword to the member declaration, as shown in the following example.</span></span>

[!code-csharp[MethodAccess](~/samples/snippets/csharp/objectoriented/accessmodifiers.cs#MethodAccess)]

## <a name="other-types"></a><span data-ttu-id="cb1f6-140">其他类型</span><span class="sxs-lookup"><span data-stu-id="cb1f6-140">Other types</span></span>

<span data-ttu-id="cb1f6-141">在命名空间内直接声明的接口可以声明为 `public` 或 `internal`，就像类和结构一样，接口默认设置为 `internal` 访问级别。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-141">Interfaces declared directly within a namespace can be `public` or `internal` and, just like classes and structs, interfaces default to `internal` access.</span></span> <span data-ttu-id="cb1f6-142">接口成员默认为 `public`，因为接口的用途是启用其他类型以访问类或结构。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-142">Interface members are `public` by default because the purpose of an interface is to enable other types to access a class or struct.</span></span> <span data-ttu-id="cb1f6-143">接口成员声明可以包含任何访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-143">Interface member declarations may include any access modifier.</span></span> <span data-ttu-id="cb1f6-144">这最适用于静态方法，以提供类的所有实现器需要的常见实现。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-144">This is most useful for static methods to provide common implementations needed by all implementors of a class.</span></span>

<span data-ttu-id="cb1f6-145">枚举成员始终为 `public`，并且不能应用任何访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-145">Enumeration members are always `public`, and no access modifiers can be applied.</span></span>

<span data-ttu-id="cb1f6-146">委托类似于类和结构。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-146">Delegates behave like classes and structs.</span></span> <span data-ttu-id="cb1f6-147">默认情况下，当在命名空间内直接声明它们时，它们具有 `internal` 访问级别，当将它们嵌套在命名空间内时，它们具有 `private` 访问级别。</span><span class="sxs-lookup"><span data-stu-id="cb1f6-147">By default, they have `internal` access when declared directly within a namespace, and `private` access when nested.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="cb1f6-148">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="cb1f6-148">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a><span data-ttu-id="cb1f6-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb1f6-149">See also</span></span>

- [<span data-ttu-id="cb1f6-150">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="cb1f6-150">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cb1f6-151">类和结构</span><span class="sxs-lookup"><span data-stu-id="cb1f6-151">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="cb1f6-152">接口</span><span class="sxs-lookup"><span data-stu-id="cb1f6-152">Interfaces</span></span>](../interfaces/index.md)
- [<span data-ttu-id="cb1f6-153">private</span><span class="sxs-lookup"><span data-stu-id="cb1f6-153">private</span></span>](../../language-reference/keywords/private.md)
- [<span data-ttu-id="cb1f6-154">public</span><span class="sxs-lookup"><span data-stu-id="cb1f6-154">public</span></span>](../../language-reference/keywords/public.md)
- [<span data-ttu-id="cb1f6-155">internal</span><span class="sxs-lookup"><span data-stu-id="cb1f6-155">internal</span></span>](../../language-reference/keywords/internal.md)
- [<span data-ttu-id="cb1f6-156">受保护</span><span class="sxs-lookup"><span data-stu-id="cb1f6-156">protected</span></span>](../../language-reference/keywords/protected.md)
- [<span data-ttu-id="cb1f6-157">protected internal</span><span class="sxs-lookup"><span data-stu-id="cb1f6-157">protected internal</span></span>](../../language-reference/keywords/protected-internal.md)
- [<span data-ttu-id="cb1f6-158">private protected</span><span class="sxs-lookup"><span data-stu-id="cb1f6-158">private protected</span></span>](../../language-reference/keywords/private-protected.md)
- [<span data-ttu-id="cb1f6-159">class</span><span class="sxs-lookup"><span data-stu-id="cb1f6-159">class</span></span>](../../language-reference/keywords/class.md)
- [<span data-ttu-id="cb1f6-160">struct</span><span class="sxs-lookup"><span data-stu-id="cb1f6-160">struct</span></span>](../../language-reference/builtin-types/struct.md)
- [<span data-ttu-id="cb1f6-161">interface</span><span class="sxs-lookup"><span data-stu-id="cb1f6-161">interface</span></span>](../../language-reference/keywords/interface.md)
