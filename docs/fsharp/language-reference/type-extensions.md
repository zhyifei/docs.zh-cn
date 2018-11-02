---
title: 类型扩展 (F#)
description: '了解如何 F # 类型扩展允许将新成员添加到以前定义的对象类型。'
ms.date: 07/20/2018
ms.openlocfilehash: 27238db1fd0803f62c32755fbc4ab7688f5c107e
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "43874974"
---
# <a name="type-extensions"></a><span data-ttu-id="96124-103">类型扩展</span><span class="sxs-lookup"><span data-stu-id="96124-103">Type extensions</span></span>

<span data-ttu-id="96124-104">类型扩展 (也称为_扩大_) 是一系列功能，让你将新成员添加到以前定义的对象类型。</span><span class="sxs-lookup"><span data-stu-id="96124-104">Type extensions (also called _augmentations_) are a family of features that let you add new members to a previously defined object type.</span></span> <span data-ttu-id="96124-105">三个功能是：</span><span class="sxs-lookup"><span data-stu-id="96124-105">The three features are:</span></span>

* <span data-ttu-id="96124-106">内部类型扩展</span><span class="sxs-lookup"><span data-stu-id="96124-106">Intrinsic type extensions</span></span>
* <span data-ttu-id="96124-107">可选类型扩展</span><span class="sxs-lookup"><span data-stu-id="96124-107">Optional type extensions</span></span>
* <span data-ttu-id="96124-108">扩展方法</span><span class="sxs-lookup"><span data-stu-id="96124-108">Extension methods</span></span>

<span data-ttu-id="96124-109">每个可用于不同方案和不同的权衡。</span><span class="sxs-lookup"><span data-stu-id="96124-109">Each can be used in different scenarios and has different tradeoffs.</span></span>

## <a name="syntax"></a><span data-ttu-id="96124-110">语法</span><span class="sxs-lookup"><span data-stu-id="96124-110">Syntax</span></span>

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

## <a name="intrinsic-type-extensions"></a><span data-ttu-id="96124-111">内部类型扩展</span><span class="sxs-lookup"><span data-stu-id="96124-111">Intrinsic type extensions</span></span>

<span data-ttu-id="96124-112">内部类型扩展是一个类型扩展，扩展的用户定义的类型。</span><span class="sxs-lookup"><span data-stu-id="96124-112">An intrinsic type extension is a type extension that extends a user-defined type.</span></span>

<span data-ttu-id="96124-113">内部类型扩展必须在同一文件中定义**和**中相同的命名空间或模块是作为正在扩展的类型。</span><span class="sxs-lookup"><span data-stu-id="96124-113">Intrinsic type extensions must be defined in the same file **and** in the same namespace or module as the type they're extending.</span></span> <span data-ttu-id="96124-114">任何其他定义将导致其正在[可选类型扩展](type-extensions.md#optional-type-extensions)。</span><span class="sxs-lookup"><span data-stu-id="96124-114">Any other definition will result in them being [optional type extensions](type-extensions.md#optional-type-extensions).</span></span>

<span data-ttu-id="96124-115">内部类型扩展有时是更简洁的方式来区分类型声明功能。</span><span class="sxs-lookup"><span data-stu-id="96124-115">Intrinsic type extensions are sometimes a cleaner way to separate functionality from the type declaration.</span></span> <span data-ttu-id="96124-116">下面的示例演示如何定义内部类型扩展：</span><span class="sxs-lookup"><span data-stu-id="96124-116">The following example shows how to define an intrinsic type extension:</span></span>

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

<span data-ttu-id="96124-117">使用类型扩展，可单独的以下各项：</span><span class="sxs-lookup"><span data-stu-id="96124-117">Using a type extension allows you to separate each of the following:</span></span>

* <span data-ttu-id="96124-118">声明`Variant`类型</span><span class="sxs-lookup"><span data-stu-id="96124-118">The declaration of a `Variant` type</span></span>
* <span data-ttu-id="96124-119">若要打印的功能`Variant`类，具体取决于其"形状"</span><span class="sxs-lookup"><span data-stu-id="96124-119">Functionality to print the `Variant` class depending on its "shape"</span></span>
* <span data-ttu-id="96124-120">用于访问对象样式使用的打印功能的方法`.`-表示法</span><span class="sxs-lookup"><span data-stu-id="96124-120">A way to access the printing functionality with object-style `.`-notation</span></span>

<span data-ttu-id="96124-121">这是一种替代方法上定义为成员的所有内容`Variant`。</span><span class="sxs-lookup"><span data-stu-id="96124-121">This is an alternative to defining everything as a member on `Variant`.</span></span> <span data-ttu-id="96124-122">虽然它不是功能的本质上是功能的更好的方法，它可以是功能的在某些情况下的更简洁表示形式。</span><span class="sxs-lookup"><span data-stu-id="96124-122">Although it is not an inherently better approach, it can be a cleaner representation of functionality in some situations.</span></span>

<span data-ttu-id="96124-123">内部类型扩展编译为它们增加时，会显示在类型上反射检查类型的类型的成员。</span><span class="sxs-lookup"><span data-stu-id="96124-123">Intrinsic type extensions are compiled as members of the type they augment, and appear on the type when the type is examined by reflection.</span></span>

## <a name="optional-type-extensions"></a><span data-ttu-id="96124-124">可选类型扩展</span><span class="sxs-lookup"><span data-stu-id="96124-124">Optional type extensions</span></span>

<span data-ttu-id="96124-125">可选类型扩展是类型的显示原始模块、 命名空间或要扩展的程序集外部的扩展。</span><span class="sxs-lookup"><span data-stu-id="96124-125">An optional type extension is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span>

<span data-ttu-id="96124-126">可选类型扩展可用于扩展具有未定义自己的类型。</span><span class="sxs-lookup"><span data-stu-id="96124-126">Optional type extensions are useful for extending a type that you have not defined yourself.</span></span> <span data-ttu-id="96124-127">例如：</span><span class="sxs-lookup"><span data-stu-id="96124-127">For example:</span></span>

```fsharp
module Extensions

open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for i in 1 .. n do
                    yield x
        }
```

<span data-ttu-id="96124-128">现在可以访问`RepeatElements`如同它是的成员<xref:System.Collections.Generic.IEnumerable%601>只要`Extensions`模块打开您正处于作用域中。</span><span class="sxs-lookup"><span data-stu-id="96124-128">You can now access `RepeatElements` as if it's a member of <xref:System.Collections.Generic.IEnumerable%601> as long as the `Extensions` module is opened in the scope that you are working in.</span></span>

<span data-ttu-id="96124-129">可选扩展不显示在当反射检查时，扩展的类型。</span><span class="sxs-lookup"><span data-stu-id="96124-129">Optional extensions do not appear on the extended type when examined by reflection.</span></span> <span data-ttu-id="96124-130">可选扩展必须在模块中，并且时，它们仅在作用域中包含扩展的模块是打开的或者在作用域中的其他方面。</span><span class="sxs-lookup"><span data-stu-id="96124-130">Optional extensions must be in modules, and they're only in scope when the module that contains the extension is open or is otherwise in scope.</span></span>

<span data-ttu-id="96124-131">可选扩展成员将会编译成静态成员，为其对象实例隐式传递的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="96124-131">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="96124-132">但是，它们的作用像是实例成员或根据它们的声明的静态成员。</span><span class="sxs-lookup"><span data-stu-id="96124-132">However, they act as if they're instance members or static members according to how they're declared.</span></span>

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a><span data-ttu-id="96124-133">泛型的内部函数和可选类型扩展限制</span><span class="sxs-lookup"><span data-stu-id="96124-133">Generic limitation of intrinsic and optional type extensions</span></span>

<span data-ttu-id="96124-134">它是可以受限类型变量的泛型类型上声明的类型扩展。</span><span class="sxs-lookup"><span data-stu-id="96124-134">It's possible to declare a type extension on a generic type where the type variable is constrained.</span></span> <span data-ttu-id="96124-135">要求是类型的扩展声明的约束与声明的约束相匹配。</span><span class="sxs-lookup"><span data-stu-id="96124-135">The requirement is that the constraint of the extension declaration matches the constraint of the declared type.</span></span>

<span data-ttu-id="96124-136">但是，即使约束匹配的声明的类型和类型扩展之间，有可能有一定比声明的类型的类型参数的不同要求的扩展成员正文推断出来的约束。</span><span class="sxs-lookup"><span data-stu-id="96124-136">However, even when constraints are matched between a declared type and a type extension, it's possible for a constraint to be inferred by the body of an extended member that imposes a different requirement on the type parameter than the declared type.</span></span> <span data-ttu-id="96124-137">例如：</span><span class="sxs-lookup"><span data-stu-id="96124-137">For example:</span></span>

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

<span data-ttu-id="96124-138">没有方法来获取此代码以使用可选类型扩展：</span><span class="sxs-lookup"><span data-stu-id="96124-138">There is no way to get this code to work with an optional type extension:</span></span>

* <span data-ttu-id="96124-139">原样`Sum`成员都有不同的约束`'T`(`static member get_Zero`和`static member (+)`) 比类型扩展的定义。</span><span class="sxs-lookup"><span data-stu-id="96124-139">As is, the `Sum` member has a different constraint on `'T` (`static member get_Zero` and `static member (+)`) than what the type extension defines.</span></span>
* <span data-ttu-id="96124-140">修改类型扩展具有同一约束作为`Sum`将不再匹配上定义的约束`IEnumerable<'T>`。</span><span class="sxs-lookup"><span data-stu-id="96124-140">Modifying the type extension to have the same constraint as `Sum` will no longer match the defined constraint on `IEnumerable<'T>`.</span></span>
* <span data-ttu-id="96124-141">进行更改的成员`member inline Sum`将产生类型约束不匹配错误</span><span class="sxs-lookup"><span data-stu-id="96124-141">Making changing the member to `member inline Sum` will give an error that type constraints are mismatched</span></span>

<span data-ttu-id="96124-142">所需的内容是"空间中浮动"，可以提供好像它们扩展类型的静态方法。</span><span class="sxs-lookup"><span data-stu-id="96124-142">What is desired are static methods that "float in space" and can be presented as if they're extending a type.</span></span> <span data-ttu-id="96124-143">这是其中的扩展方法变得非常必要。</span><span class="sxs-lookup"><span data-stu-id="96124-143">This is where extension methods become necessary.</span></span>

## <a name="extension-methods"></a><span data-ttu-id="96124-144">扩展方法</span><span class="sxs-lookup"><span data-stu-id="96124-144">Extension methods</span></span>

<span data-ttu-id="96124-145">最后，扩展方法 （有时称为"C# 样式扩展成员"） 可以声明在 F # 中为静态成员方法的类上。</span><span class="sxs-lookup"><span data-stu-id="96124-145">Finally, extension methods (sometimes called "C# style extension members") can be declared in F# as a static member method on a class.</span></span>

<span data-ttu-id="96124-146">扩展方法可用于当你希望将约束类型变量的泛型类型上定义扩展。</span><span class="sxs-lookup"><span data-stu-id="96124-146">Extension methods are useful for when you wish to define extensions on a generic type that will constrain the type variable.</span></span> <span data-ttu-id="96124-147">例如：</span><span class="sxs-lookup"><span data-stu-id="96124-147">For example:</span></span>

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="96124-148">使用时，此代码将使其看起来像`Sum`上定义<xref:System.Collections.Generic.IEnumerable%601>，但前提是`Extensions`已打开或在范围内。</span><span class="sxs-lookup"><span data-stu-id="96124-148">When used, this code will make it appear as if `Sum` is defined on <xref:System.Collections.Generic.IEnumerable%601>, so long as `Extensions` has been opened or is in scope.</span></span>

## <a name="other-remarks"></a><span data-ttu-id="96124-149">其他备注</span><span class="sxs-lookup"><span data-stu-id="96124-149">Other remarks</span></span>

<span data-ttu-id="96124-150">类型扩展还具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="96124-150">Type extensions also have the following attributes:</span></span>

* <span data-ttu-id="96124-151">可以扩展任何可访问的类型。</span><span class="sxs-lookup"><span data-stu-id="96124-151">Any type that can be accessed can be extended.</span></span>
* <span data-ttu-id="96124-152">可以定义内部函数和可选类型扩展_任何_成员类型，而不仅仅是方法。</span><span class="sxs-lookup"><span data-stu-id="96124-152">Intrinsic and optional type extensions can define _any_ member type, not just methods.</span></span> <span data-ttu-id="96124-153">因此扩展属性也有可能，例如。</span><span class="sxs-lookup"><span data-stu-id="96124-153">So extension properties are also possible, for example.</span></span>
* <span data-ttu-id="96124-154">`self-identifier`令牌[语法](type-extensions.md#syntax)表示调用，就像普通成员的类型的实例。</span><span class="sxs-lookup"><span data-stu-id="96124-154">The `self-identifier` token in the [syntax](type-extensions.md#syntax) represents the instance of the type being invoked, just like ordinary members.</span></span>
* <span data-ttu-id="96124-155">扩展的成员可以是静态或实例成员。</span><span class="sxs-lookup"><span data-stu-id="96124-155">Extended members can be static or instance members.</span></span>
* <span data-ttu-id="96124-156">在类型扩展的类型变量必须与匹配的声明类型的约束。</span><span class="sxs-lookup"><span data-stu-id="96124-156">Type variables on a type extension must match the constraints of the declared type.</span></span>

<span data-ttu-id="96124-157">类型扩展还存在以下限制：</span><span class="sxs-lookup"><span data-stu-id="96124-157">The following limitations also exist for type extensions:</span></span>

* <span data-ttu-id="96124-158">类型扩展不支持虚拟或抽象方法。</span><span class="sxs-lookup"><span data-stu-id="96124-158">Type extensions do not support virtual or abstract methods.</span></span>
* <span data-ttu-id="96124-159">类型扩展不支持扩大作为替代方法。</span><span class="sxs-lookup"><span data-stu-id="96124-159">Type extensions do not support override methods as augmentations.</span></span>
* <span data-ttu-id="96124-160">不支持类型扩展[静态解析的类型参数](generics/statically-resolved-type-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="96124-160">Type extensions do not support [Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md).</span></span>
* <span data-ttu-id="96124-161">可选类型扩展不支持扩大作为构造函数。</span><span class="sxs-lookup"><span data-stu-id="96124-161">Optional Type extensions do not support constructors as augmentations.</span></span>
* <span data-ttu-id="96124-162">不能在定义类型扩展[类型缩写，用](type-abbreviations.md)。</span><span class="sxs-lookup"><span data-stu-id="96124-162">Type extensions cannot be defined on [type abbreviations](type-abbreviations.md).</span></span>
* <span data-ttu-id="96124-163">类型扩展不是有效的`byref<'T>`（尽管它们可以声明）。</span><span class="sxs-lookup"><span data-stu-id="96124-163">Type extensions are not valid for `byref<'T>` (though they can be declared).</span></span>
* <span data-ttu-id="96124-164">类型扩展不是有效的属性 （但它们可以声明）。</span><span class="sxs-lookup"><span data-stu-id="96124-164">Type extensions are not valid for attributes (though they can be declared).</span></span>
* <span data-ttu-id="96124-165">可以定义重载具有相同名称的其他方法的扩展，但 F # 编译器提供了首选项设置为非扩展方法，如果调用不明确。</span><span class="sxs-lookup"><span data-stu-id="96124-165">You can define extensions that overload other methods of the same name, but the F# compiler gives preference to non-extension methods if there is an ambiguous call.</span></span>

<span data-ttu-id="96124-166">最后，如果多个内部类型扩展存在一种类型，所有成员必须都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="96124-166">Finally, if multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="96124-167">对于可选类型扩展为同一类型的不同类型扩展中的成员可以具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="96124-167">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="96124-168">仅当客户端代码打开两个不同的作用域定义相同成员名称，则会出现多义性错误。</span><span class="sxs-lookup"><span data-stu-id="96124-168">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

## <a name="see-also"></a><span data-ttu-id="96124-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="96124-169">See also</span></span>

- [<span data-ttu-id="96124-170">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="96124-170">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="96124-171">成员</span><span class="sxs-lookup"><span data-stu-id="96124-171">Members</span></span>](members/index.md)
