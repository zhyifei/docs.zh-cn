---
title: 结构
description: 了解F#结构, 对于具有少量数据和简单行为的类型, 精简对象类型通常比类更有效。
ms.date: 05/16/2016
ms.openlocfilehash: e638b450fe43e0993c9980cade246c3f26d25e2d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630769"
---
# <a name="structures"></a><span data-ttu-id="b2ebf-103">结构</span><span class="sxs-lookup"><span data-stu-id="b2ebf-103">Structures</span></span>

<span data-ttu-id="b2ebf-104">*结构*是一种紧凑对象类型, 它比具有少量数据和简单行为的类型的类更有效。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-104">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="b2ebf-105">语法</span><span class="sxs-lookup"><span data-stu-id="b2ebf-105">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements-and-members
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements-and-members
```

## <a name="remarks"></a><span data-ttu-id="b2ebf-106">备注</span><span class="sxs-lookup"><span data-stu-id="b2ebf-106">Remarks</span></span>

<span data-ttu-id="b2ebf-107">结构是*值类型*, 这意味着它们直接存储在堆栈上, 或者作为字段或数组元素使用内联在父类型中。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-107">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="b2ebf-108">与类和记录不同，结构具有按值传递语义。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-108">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="b2ebf-109">这意味着它们主要用于经常访问和复制的少量聚合数据。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-109">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="b2ebf-110">在前面的语法中，将显示两个窗体。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-110">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="b2ebf-111">第一个窗体不是轻量级语法，但其仍然经常使用，因为当使用 `struct` 和 `end` 关键字时，你可以忽略第二个窗体中出现的 `StructAttribute` 特性。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-111">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="b2ebf-112">你可以将 `StructAttribute` 缩写为 `Struct`。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-112">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="b2ebf-113">前面的语法中的*类型定义元素和成员*表示成员声明和定义。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-113">The *type-definition-elements-and-members* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="b2ebf-114">结构可以具有构造函数以及可变和不可变字段，并且可以声明成员和接口实现。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-114">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="b2ebf-115">有关详细信息, 请参阅[成员](./members/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-115">For more information, see [Members](./members/index.md).</span></span>

<span data-ttu-id="b2ebf-116">结构不能参与继承、不能包含 `let` 或 `do` 绑定、不能以递归方式包含其自身类型的字段（但可以包含引用其自身类型的引用单元格）。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-116">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="b2ebf-117">由于结构不允许 `let` 绑定，你必须通过使用 `val` 关键字在结构中声明字段。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-117">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="b2ebf-118">`val` 关键字定义字段及其类型，但不允许初始化。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-118">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="b2ebf-119">相反，`val` 声明会初始化零或 null。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-119">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="b2ebf-120">因此，具有隐式构造函数（即，在声明中的结构名称后直接给定参数）的结构要求使用 `val` 特性批注 `DefaultValue` 声明。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-120">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="b2ebf-121">具有定义构造函数的结构仍支持零初始化。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-121">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="b2ebf-122">因此，`DefaultValue` 特性是此类零值对字段有效的声明。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-122">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="b2ebf-123">由于此类型上不允许 `let` 和 `do` 绑定，结构的隐式构造函数不执行任何操作，但所传入的隐式构造函数参数值作为私有字段提供。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-123">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="b2ebf-124">显式构造函数可能涉及字段值的初始化。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-124">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="b2ebf-125">当你的结构具有显式构造函数时，它仍支持零初始化；但是，由于它与显式构造函数冲突，请勿在 `DefaultValue` 声明上使用 `val` 特性。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-125">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="b2ebf-126">有关`val`声明的详细信息, 请[参阅显式字段:`val`关键字。](./members/explicit-fields-the-val-keyword.md)</span><span class="sxs-lookup"><span data-stu-id="b2ebf-126">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="b2ebf-127">结构上允许特性和可访问性修饰符，并遵循与其他类型相同的规则。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-127">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="b2ebf-128">有关详细信息, 请参阅[特性](attributes.md)和[访问控制](access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-128">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="b2ebf-129">以下代码示例说明结构定义。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-129">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a><span data-ttu-id="b2ebf-130">ByRefLike 结构</span><span class="sxs-lookup"><span data-stu-id="b2ebf-130">ByRefLike structs</span></span>

<span data-ttu-id="b2ebf-131">您可以定义自己的结构, 这些结构可以`byref`遵循类似的语义: 有关详细信息, 请参阅[byref](byrefs.md) 。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-131">You can define your own structs that can adhere to `byref`-like semantics: see [Byrefs](byrefs.md) for more information.</span></span> <span data-ttu-id="b2ebf-132">此操作通过 <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> 属性实现：</span><span class="sxs-lookup"><span data-stu-id="b2ebf-132">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="b2ebf-133">`IsByRefLike`不意味着`Struct`。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-133">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="b2ebf-134">这两者都必须存在于类型上。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-134">Both must be present on the type.</span></span>

<span data-ttu-id="b2ebf-135">中F#的`byref`"like" 结构是堆栈绑定值类型。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-135">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="b2ebf-136">永远不会在托管堆上分配。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-136">It is never allocated on the managed heap.</span></span> <span data-ttu-id="b2ebf-137">`byref`类似的结构可用于实现高性能编程, 因为它是针对生存期和非捕获的一组强检查强制实施的。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-137">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="b2ebf-138">规则如下:</span><span class="sxs-lookup"><span data-stu-id="b2ebf-138">The rules are:</span></span>

* <span data-ttu-id="b2ebf-139">它们可用作函数参数、方法参数、局部变量、方法返回。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-139">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="b2ebf-140">它们不能是类或普通结构的静态成员或实例成员。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-140">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="b2ebf-141">它们不能由任何闭包构造 (`async`方法或 lambda 表达式) 捕获。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-141">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="b2ebf-142">它们不能用作泛型参数。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-142">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="b2ebf-143">尽管这些规则非常严格地限制使用, 但它们会以安全的方式满足高性能计算的承诺。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-143">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="b2ebf-144">ReadOnly 结构</span><span class="sxs-lookup"><span data-stu-id="b2ebf-144">ReadOnly structs</span></span>

<span data-ttu-id="b2ebf-145">您可以用<xref:System.Runtime.CompilerServices.IsReadOnlyAttribute>属性批注结构。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-145">You can annotate structs with the <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> attribute.</span></span> <span data-ttu-id="b2ebf-146">例如：</span><span class="sxs-lookup"><span data-stu-id="b2ebf-146">For example:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="b2ebf-147">`IsReadOnly`不意味着`Struct`。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-147">`IsReadOnly` does not imply `Struct`.</span></span> <span data-ttu-id="b2ebf-148">必须同时添加这两个, `IsReadOnly`才能获得结构。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-148">You must add both to have an `IsReadOnly` struct.</span></span>

<span data-ttu-id="b2ebf-149">使用此属性将发出元数据F# , C#让和知道将其`inref<'T>`分别`in ref`作为和处理。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-149">Use of this attribute emits metadata letting F# and C# know to treat it as `inref<'T>` and `in ref`, respectively.</span></span>

<span data-ttu-id="b2ebf-150">在 readonly 结构内定义可变值将产生错误。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-150">Defining a mutable value inside of a readonly struct produces an error.</span></span>

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="b2ebf-151">结构记录和可区分联合</span><span class="sxs-lookup"><span data-stu-id="b2ebf-151">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="b2ebf-152">可以将[记录](records.md)和可[区分联合](discriminated-unions.md)表示为具有特性`[<Struct>]`的结构。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-152">You can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="b2ebf-153">请参阅每篇文章了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2ebf-153">See each article to learn more.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2ebf-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2ebf-154">See also</span></span>

- [<span data-ttu-id="b2ebf-155">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="b2ebf-155">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="b2ebf-156">类</span><span class="sxs-lookup"><span data-stu-id="b2ebf-156">Classes</span></span>](classes.md)
- [<span data-ttu-id="b2ebf-157">记录</span><span class="sxs-lookup"><span data-stu-id="b2ebf-157">Records</span></span>](records.md)
- [<span data-ttu-id="b2ebf-158">成员</span><span class="sxs-lookup"><span data-stu-id="b2ebf-158">Members</span></span>](./members/index.md)
