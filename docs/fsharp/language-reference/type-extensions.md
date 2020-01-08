---
title: 类型扩展
description: 了解如何F#通过类型扩展将新成员添加到之前定义的对象类型。
ms.date: 11/04/2019
ms.openlocfilehash: 3e2c6971156bd562ed5d5428e6b7ffdc520c4cf5
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75341572"
---
# <a name="type-extensions"></a><span data-ttu-id="a5ede-103">类型扩展</span><span class="sxs-lookup"><span data-stu-id="a5ede-103">Type extensions</span></span>

<span data-ttu-id="a5ede-104">类型扩展（也称为_扩大_）是一系列功能，使你可以向之前定义的对象类型添加新成员。</span><span class="sxs-lookup"><span data-stu-id="a5ede-104">Type extensions (also called _augmentations_) are a family of features that let you add new members to a previously defined object type.</span></span> <span data-ttu-id="a5ede-105">这三种功能包括：</span><span class="sxs-lookup"><span data-stu-id="a5ede-105">The three features are:</span></span>

- <span data-ttu-id="a5ede-106">内部类型扩展</span><span class="sxs-lookup"><span data-stu-id="a5ede-106">Intrinsic type extensions</span></span>
- <span data-ttu-id="a5ede-107">可选类型扩展</span><span class="sxs-lookup"><span data-stu-id="a5ede-107">Optional type extensions</span></span>
- <span data-ttu-id="a5ede-108">扩展方法</span><span class="sxs-lookup"><span data-stu-id="a5ede-108">Extension methods</span></span>

<span data-ttu-id="a5ede-109">每个可以在不同的方案中使用，并且具有不同的折衷。</span><span class="sxs-lookup"><span data-stu-id="a5ede-109">Each can be used in different scenarios and has different tradeoffs.</span></span>

## <a name="syntax"></a><span data-ttu-id="a5ede-110">语法</span><span class="sxs-lookup"><span data-stu-id="a5ede-110">Syntax</span></span>

```fsharp
// Intrinsic and optional extensions
type typename with
    member self-identifier.member-name =
        body
    ...

// Extension methods
open System.Runtime.CompilerServices

[<Extension>]
type Extensions() =
    [static] member self-identifier.extension-name (ty: typename, [args]) =
        body
    ...
```

## <a name="intrinsic-type-extensions"></a><span data-ttu-id="a5ede-111">内部类型扩展</span><span class="sxs-lookup"><span data-stu-id="a5ede-111">Intrinsic type extensions</span></span>

<span data-ttu-id="a5ede-112">内部类型扩展是扩展用户定义类型的类型扩展。</span><span class="sxs-lookup"><span data-stu-id="a5ede-112">An intrinsic type extension is a type extension that extends a user-defined type.</span></span>

<span data-ttu-id="a5ede-113">内部类型扩展必须在同一文件中定义 **，并**在与它们所扩展的类型相同的命名空间或模块中定义。</span><span class="sxs-lookup"><span data-stu-id="a5ede-113">Intrinsic type extensions must be defined in the same file **and** in the same namespace or module as the type they're extending.</span></span> <span data-ttu-id="a5ede-114">任何其他定义都将导致其成为[可选类型扩展](type-extensions.md#optional-type-extensions)。</span><span class="sxs-lookup"><span data-stu-id="a5ede-114">Any other definition will result in them being [optional type extensions](type-extensions.md#optional-type-extensions).</span></span>

<span data-ttu-id="a5ede-115">内部类型扩展有时是将功能与类型声明分开的更清晰的方式。</span><span class="sxs-lookup"><span data-stu-id="a5ede-115">Intrinsic type extensions are sometimes a cleaner way to separate functionality from the type declaration.</span></span> <span data-ttu-id="a5ede-116">下面的示例演示如何定义内部类型扩展：</span><span class="sxs-lookup"><span data-stu-id="a5ede-116">The following example shows how to define an intrinsic type extension:</span></span>

```fsharp
namespace Example

type Variant =
    | Num of int
    | Str of string
  
module Variant =
    let print v =
        match v with
        | Num n -> printf "Num %d" n
        | Str s -> printf "Str %s" s

// Add a member to Variant as an extension
type Variant with
    member x.Print() = Variant.print x
```

<span data-ttu-id="a5ede-117">使用类型扩展可以分隔以下各项：</span><span class="sxs-lookup"><span data-stu-id="a5ede-117">Using a type extension allows you to separate each of the following:</span></span>

- <span data-ttu-id="a5ede-118">`Variant` 类型的声明</span><span class="sxs-lookup"><span data-stu-id="a5ede-118">The declaration of a `Variant` type</span></span>
- <span data-ttu-id="a5ede-119">用于根据 "形状" 打印 `Variant` 类的功能</span><span class="sxs-lookup"><span data-stu-id="a5ede-119">Functionality to print the `Variant` class depending on its "shape"</span></span>
- <span data-ttu-id="a5ede-120">使用对象样式 `.`表示法访问打印功能的一种方法</span><span class="sxs-lookup"><span data-stu-id="a5ede-120">A way to access the printing functionality with object-style `.`-notation</span></span>

<span data-ttu-id="a5ede-121">这是将所有内容定义为 `Variant`上的成员的替代方法。</span><span class="sxs-lookup"><span data-stu-id="a5ede-121">This is an alternative to defining everything as a member on `Variant`.</span></span> <span data-ttu-id="a5ede-122">尽管它不是原本更好的方法，但在某些情况下，它可能是功能的更清晰表示形式。</span><span class="sxs-lookup"><span data-stu-id="a5ede-122">Although it is not an inherently better approach, it can be a cleaner representation of functionality in some situations.</span></span>

<span data-ttu-id="a5ede-123">内部类型扩展将编译为它们增加的类型的成员，并在反射检查类型时在类型上显示。</span><span class="sxs-lookup"><span data-stu-id="a5ede-123">Intrinsic type extensions are compiled as members of the type they augment, and appear on the type when the type is examined by reflection.</span></span>

## <a name="optional-type-extensions"></a><span data-ttu-id="a5ede-124">可选类型扩展</span><span class="sxs-lookup"><span data-stu-id="a5ede-124">Optional type extensions</span></span>

<span data-ttu-id="a5ede-125">可选类型扩展是在要扩展的类型的原始模块、命名空间或程序集的外部显示的扩展。</span><span class="sxs-lookup"><span data-stu-id="a5ede-125">An optional type extension is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span>

<span data-ttu-id="a5ede-126">可选类型扩展对于扩展你自己尚未定义的类型很有用。</span><span class="sxs-lookup"><span data-stu-id="a5ede-126">Optional type extensions are useful for extending a type that you have not defined yourself.</span></span> <span data-ttu-id="a5ede-127">例如：</span><span class="sxs-lookup"><span data-stu-id="a5ede-127">For example:</span></span>

```fsharp
module Extensions

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for _ in 1 .. n -> x
        }
```

<span data-ttu-id="a5ede-128">你现在可以访问 `RepeatElements`，就像它是 <xref:System.Collections.Generic.IEnumerable%601> 的成员，前提是 `Extensions` 模块是在你所使用的范围中打开的。</span><span class="sxs-lookup"><span data-stu-id="a5ede-128">You can now access `RepeatElements` as if it's a member of <xref:System.Collections.Generic.IEnumerable%601> as long as the `Extensions` module is opened in the scope that you are working in.</span></span>

<span data-ttu-id="a5ede-129">可选扩展在由反射检查时不会出现在扩展类型上。</span><span class="sxs-lookup"><span data-stu-id="a5ede-129">Optional extensions do not appear on the extended type when examined by reflection.</span></span> <span data-ttu-id="a5ede-130">可选扩展必须在模块中，且仅当包含该扩展的模块处于打开状态或处于范围内时，它们才在范围内。</span><span class="sxs-lookup"><span data-stu-id="a5ede-130">Optional extensions must be in modules, and they're only in scope when the module that contains the extension is open or is otherwise in scope.</span></span>

<span data-ttu-id="a5ede-131">可选扩展成员将编译为静态成员，其对象实例将被隐式传递为第一个参数。</span><span class="sxs-lookup"><span data-stu-id="a5ede-131">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="a5ede-132">但是，它们的作用就像是实例成员或静态成员的声明方式。</span><span class="sxs-lookup"><span data-stu-id="a5ede-132">However, they act as if they're instance members or static members according to how they're declared.</span></span>

<span data-ttu-id="a5ede-133">可选扩展成员也不适用于C#或 Visual Basic 使用者。</span><span class="sxs-lookup"><span data-stu-id="a5ede-133">Optional extension members are also not visible to C# or Visual Basic consumers.</span></span> <span data-ttu-id="a5ede-134">它们只能在其他F#代码中使用。</span><span class="sxs-lookup"><span data-stu-id="a5ede-134">They can only be consumed in other F# code.</span></span>

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a><span data-ttu-id="a5ede-135">内部和可选类型扩展的泛型限制</span><span class="sxs-lookup"><span data-stu-id="a5ede-135">Generic limitation of intrinsic and optional type extensions</span></span>

<span data-ttu-id="a5ede-136">可以在类型变量受到约束的泛型类型上声明类型扩展。</span><span class="sxs-lookup"><span data-stu-id="a5ede-136">It's possible to declare a type extension on a generic type where the type variable is constrained.</span></span> <span data-ttu-id="a5ede-137">要求是扩展声明的约束与声明类型的约束匹配。</span><span class="sxs-lookup"><span data-stu-id="a5ede-137">The requirement is that the constraint of the extension declaration matches the constraint of the declared type.</span></span>

<span data-ttu-id="a5ede-138">但是，即使在声明的类型和类型扩展之间进行了匹配，约束仍有可能由扩展成员的主体推断，该扩展成员在类型参数上施加不同于声明类型的要求。</span><span class="sxs-lookup"><span data-stu-id="a5ede-138">However, even when constraints are matched between a declared type and a type extension, it's possible for a constraint to be inferred by the body of an extended member that imposes a different requirement on the type parameter than the declared type.</span></span> <span data-ttu-id="a5ede-139">例如：</span><span class="sxs-lookup"><span data-stu-id="a5ede-139">For example:</span></span>

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

<span data-ttu-id="a5ede-140">无法获取此代码以使用可选类型扩展：</span><span class="sxs-lookup"><span data-stu-id="a5ede-140">There is no way to get this code to work with an optional type extension:</span></span>

- <span data-ttu-id="a5ede-141">同样，`Sum` 成员对 `'T` （`static member get_Zero` 和 `static member (+)`）具有不同于类型扩展所定义的约束。</span><span class="sxs-lookup"><span data-stu-id="a5ede-141">As is, the `Sum` member has a different constraint on `'T` (`static member get_Zero` and `static member (+)`) than what the type extension defines.</span></span>
- <span data-ttu-id="a5ede-142">修改类型扩展以与 `Sum` 具有相同的约束将不再与 `IEnumerable<'T>`上定义的约束匹配。</span><span class="sxs-lookup"><span data-stu-id="a5ede-142">Modifying the type extension to have the same constraint as `Sum` will no longer match the defined constraint on `IEnumerable<'T>`.</span></span>
- <span data-ttu-id="a5ede-143">将 `member this.Sum` 更改为 `member inline this.Sum` 将给出类型约束不匹配的错误。</span><span class="sxs-lookup"><span data-stu-id="a5ede-143">Changing `member this.Sum` to `member inline this.Sum` will give an error that type constraints are mismatched.</span></span>

<span data-ttu-id="a5ede-144">所需的是 "在空间中浮动" 的静态方法，并可以显示为扩展类型。</span><span class="sxs-lookup"><span data-stu-id="a5ede-144">What is desired are static methods that "float in space" and can be presented as if they're extending a type.</span></span> <span data-ttu-id="a5ede-145">这就是需要扩展方法的地方。</span><span class="sxs-lookup"><span data-stu-id="a5ede-145">This is where extension methods become necessary.</span></span>

## <a name="extension-methods"></a><span data-ttu-id="a5ede-146">扩展方法</span><span class="sxs-lookup"><span data-stu-id="a5ede-146">Extension methods</span></span>

<span data-ttu-id="a5ede-147">最后，扩展方法（有时称为 "C#样式扩展成员"）可以作为类的F#静态成员方法在中声明。</span><span class="sxs-lookup"><span data-stu-id="a5ede-147">Finally, extension methods (sometimes called "C# style extension members") can be declared in F# as a static member method on a class.</span></span>

<span data-ttu-id="a5ede-148">当您希望在将约束类型变量的泛型类型上定义扩展时，扩展方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="a5ede-148">Extension methods are useful for when you wish to define extensions on a generic type that will constrain the type variable.</span></span> <span data-ttu-id="a5ede-149">例如：</span><span class="sxs-lookup"><span data-stu-id="a5ede-149">For example:</span></span>

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="a5ede-150">使用时，此代码将使其看起来就像 <xref:System.Collections.Generic.IEnumerable%601>上定义 `Sum`，只要 `Extensions` 已打开或在范围内。</span><span class="sxs-lookup"><span data-stu-id="a5ede-150">When used, this code will make it appear as if `Sum` is defined on <xref:System.Collections.Generic.IEnumerable%601>, so long as `Extensions` has been opened or is in scope.</span></span>

## <a name="other-remarks"></a><span data-ttu-id="a5ede-151">其他备注</span><span class="sxs-lookup"><span data-stu-id="a5ede-151">Other remarks</span></span>

<span data-ttu-id="a5ede-152">类型扩展还具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="a5ede-152">Type extensions also have the following attributes:</span></span>

- <span data-ttu-id="a5ede-153">可访问的任何类型都可以进行扩展。</span><span class="sxs-lookup"><span data-stu-id="a5ede-153">Any type that can be accessed can be extended.</span></span>
- <span data-ttu-id="a5ede-154">内部和可选类型扩展可以定义_任何_成员类型，而不仅仅是方法。</span><span class="sxs-lookup"><span data-stu-id="a5ede-154">Intrinsic and optional type extensions can define _any_ member type, not just methods.</span></span> <span data-ttu-id="a5ede-155">例如，也可以扩展属性。</span><span class="sxs-lookup"><span data-stu-id="a5ede-155">So extension properties are also possible, for example.</span></span>
- <span data-ttu-id="a5ede-156">[语法](type-extensions.md#syntax)中的`self-identifier`标记表示正在调用的类型的实例, 就像普通成员一样。</span><span class="sxs-lookup"><span data-stu-id="a5ede-156">The `self-identifier` token in the [syntax](type-extensions.md#syntax) represents the instance of the type being invoked, just like ordinary members.</span></span>
- <span data-ttu-id="a5ede-157">扩展成员可以是静态成员或实例成员。</span><span class="sxs-lookup"><span data-stu-id="a5ede-157">Extended members can be static or instance members.</span></span>
- <span data-ttu-id="a5ede-158">类型扩展上的类型变量必须与声明类型的约束匹配。</span><span class="sxs-lookup"><span data-stu-id="a5ede-158">Type variables on a type extension must match the constraints of the declared type.</span></span>

<span data-ttu-id="a5ede-159">对于类型扩展也存在以下限制：</span><span class="sxs-lookup"><span data-stu-id="a5ede-159">The following limitations also exist for type extensions:</span></span>

- <span data-ttu-id="a5ede-160">类型扩展不支持虚拟或抽象方法。</span><span class="sxs-lookup"><span data-stu-id="a5ede-160">Type extensions do not support virtual or abstract methods.</span></span>
- <span data-ttu-id="a5ede-161">类型扩展不支持作为扩大的重写方法。</span><span class="sxs-lookup"><span data-stu-id="a5ede-161">Type extensions do not support override methods as augmentations.</span></span>
- <span data-ttu-id="a5ede-162">类型扩展不支持[静态解析的类型参数](./generics/statically-resolved-type-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="a5ede-162">Type extensions do not support [Statically Resolved Type Parameters](./generics/statically-resolved-type-parameters.md).</span></span>
- <span data-ttu-id="a5ede-163">可选类型扩展不支持作为扩大的构造函数。</span><span class="sxs-lookup"><span data-stu-id="a5ede-163">Optional Type extensions do not support constructors as augmentations.</span></span>
- <span data-ttu-id="a5ede-164">不能对[类型缩写](type-abbreviations.md)定义类型扩展。</span><span class="sxs-lookup"><span data-stu-id="a5ede-164">Type extensions cannot be defined on [type abbreviations](type-abbreviations.md).</span></span>
- <span data-ttu-id="a5ede-165">类型扩展对于 `byref<'T>` 无效（尽管可以声明）。</span><span class="sxs-lookup"><span data-stu-id="a5ede-165">Type extensions are not valid for `byref<'T>` (though they can be declared).</span></span>
- <span data-ttu-id="a5ede-166">类型扩展对于特性无效（尽管它们可以声明）。</span><span class="sxs-lookup"><span data-stu-id="a5ede-166">Type extensions are not valid for attributes (though they can be declared).</span></span>
- <span data-ttu-id="a5ede-167">您可以定义重载同名其他方法的扩展，但F#编译器会在出现不明确的调用时为非扩展方法提供首选项。</span><span class="sxs-lookup"><span data-stu-id="a5ede-167">You can define extensions that overload other methods of the same name, but the F# compiler gives preference to non-extension methods if there is an ambiguous call.</span></span>

<span data-ttu-id="a5ede-168">最后，如果一种类型存在多个内部类型扩展，则所有成员都必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a5ede-168">Finally, if multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="a5ede-169">对于可选类型扩展，不同类型扩展中具有相同类型的成员可以具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="a5ede-169">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="a5ede-170">仅当客户端代码打开两个不同的作用域定义相同的成员名称时，才会发生多义性错误。</span><span class="sxs-lookup"><span data-stu-id="a5ede-170">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5ede-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5ede-171">See also</span></span>

- [<span data-ttu-id="a5ede-172">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="a5ede-172">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="a5ede-173">成员</span><span class="sxs-lookup"><span data-stu-id="a5ede-173">Members</span></span>](./members/index.md)
