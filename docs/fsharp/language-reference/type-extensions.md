---
title: "类型扩展 (F#)"
description: "了解如何 F # 类型扩展允许将新成员添加到以前定义的对象类型。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c9d7ce27-f5ad-4766-b9e9-34187da5bc24
ms.openlocfilehash: f78f8689e95fc1547f1a2b17c615592c00051f7c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="type-extensions"></a><span data-ttu-id="99794-104">类型扩展</span><span class="sxs-lookup"><span data-stu-id="99794-104">Type Extensions</span></span>

<span data-ttu-id="99794-105">类型扩展允许你将新成员添加到以前定义的对象类型。</span><span class="sxs-lookup"><span data-stu-id="99794-105">Type extensions let you add new members to a previously defined object type.</span></span>

## <a name="syntax"></a><span data-ttu-id="99794-106">语法</span><span class="sxs-lookup"><span data-stu-id="99794-106">Syntax</span></span>

```fsharp
// Intrinsic extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]

// Optional extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]
```

## <a name="remarks"></a><span data-ttu-id="99794-107">备注</span><span class="sxs-lookup"><span data-stu-id="99794-107">Remarks</span></span>
<span data-ttu-id="99794-108">有两种形式的具有略有不同的语法和行为的类型扩展。</span><span class="sxs-lookup"><span data-stu-id="99794-108">There are two forms of type extensions that have slightly different syntax and behavior.</span></span> <span data-ttu-id="99794-109">*内部扩展*作为要扩展的类型是相同的命名空间或模块中，在同一源文件中，，而在同一程序集 （DLL 或可执行文件） 的扩展。</span><span class="sxs-lookup"><span data-stu-id="99794-109">An *intrinsic extension* is an extension that appears in the same namespace or module, in the same source file, and in the same assembly (DLL or executable file) as the type being extended.</span></span> <span data-ttu-id="99794-110">*可选扩展*是显示原始的模块、 命名空间或要扩展的类型的程序集外部的扩展。</span><span class="sxs-lookup"><span data-stu-id="99794-110">An *optional extension* is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span> <span data-ttu-id="99794-111">类型检查通过反射，但可选扩展不这样做时，内部扩展会出现在类型上。</span><span class="sxs-lookup"><span data-stu-id="99794-111">Intrinsic extensions appear on the type when the type is examined by reflection, but optional extensions do not.</span></span> <span data-ttu-id="99794-112">可选扩展必须在模块中，并且它们是仅在作用域中打开包含扩展的模块时。</span><span class="sxs-lookup"><span data-stu-id="99794-112">Optional extensions must be in modules, and they are only in scope when the module that contains the extension is open.</span></span>

<span data-ttu-id="99794-113">在上述语法中， *typename*表示要扩展的类型。</span><span class="sxs-lookup"><span data-stu-id="99794-113">In the previous syntax, *typename* represents the type that is being extended.</span></span> <span data-ttu-id="99794-114">可以扩展可访问任何类型，但类型名称必须是一个实际类型名称，而不是类型缩写。</span><span class="sxs-lookup"><span data-stu-id="99794-114">Any type that can be accessed can be extended, but the type name must be an actual type name, not a type abbreviation.</span></span> <span data-ttu-id="99794-115">一种类型扩展中，可以定义多个成员。</span><span class="sxs-lookup"><span data-stu-id="99794-115">You can define multiple members in one type extension.</span></span> <span data-ttu-id="99794-116">*自我标识符*表示正在调用，就像普通成员中一样的对象的实例。</span><span class="sxs-lookup"><span data-stu-id="99794-116">The *self-identifier* represents the instance of the object being invoked, just as in ordinary members.</span></span>

<span data-ttu-id="99794-117">`end`关键字是轻量语法中可选的。</span><span class="sxs-lookup"><span data-stu-id="99794-117">The `end` keyword is optional in lightweight syntax.</span></span>

<span data-ttu-id="99794-118">类型扩展中定义的成员可对类类型上的其他成员一样。</span><span class="sxs-lookup"><span data-stu-id="99794-118">Members defined in type extensions can be used just like other members on a class type.</span></span> <span data-ttu-id="99794-119">与其他成员一样，它们可以是静态或实例成员。</span><span class="sxs-lookup"><span data-stu-id="99794-119">Like other members, they can be static or instance members.</span></span> <span data-ttu-id="99794-120">这些方法是也称为*扩展方法*; 属性被称为*扩展属性*，依次类推。</span><span class="sxs-lookup"><span data-stu-id="99794-120">These methods are also known as *extension methods*; properties are known as *extension properties*, and so on.</span></span> <span data-ttu-id="99794-121">可选扩展成员被编译到的对象实例隐式作为传递的第一个参数的静态成员。</span><span class="sxs-lookup"><span data-stu-id="99794-121">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="99794-122">但是，它们充当就像它们是实例成员或根据声明方式的静态成员。</span><span class="sxs-lookup"><span data-stu-id="99794-122">However, they act as if they were instance members or static members according to how they are declared.</span></span> <span data-ttu-id="99794-123">隐式扩展成员包括作为该类型的成员，可以使用不受限制。</span><span class="sxs-lookup"><span data-stu-id="99794-123">Implicit extension members are included as members of the type and can be used without restriction.</span></span>

<span data-ttu-id="99794-124">扩展方法不能为虚拟或抽象方法。</span><span class="sxs-lookup"><span data-stu-id="99794-124">Extension methods cannot be virtual or abstract methods.</span></span> <span data-ttu-id="99794-125">它们可以重载具有相同名称的其他方法，但编译器则报告首选项设置为对于不明确的调用的非扩展方法。</span><span class="sxs-lookup"><span data-stu-id="99794-125">They can overload other methods of the same name, but the compiler gives preference to non-extension methods in the case of an ambiguous call.</span></span>

<span data-ttu-id="99794-126">如果一个类型的存在多个内部类型扩展，所有成员必须都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="99794-126">If multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="99794-127">对于可选类型扩展，为同一类型的不同类型扩展中的成员可以具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="99794-127">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="99794-128">仅当客户端代码将打开两个不同的作用域定义相同的成员名称，则会出现多义性错误。</span><span class="sxs-lookup"><span data-stu-id="99794-128">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

<span data-ttu-id="99794-129">在下面的示例中，模块中的类型有内部类型扩展。</span><span class="sxs-lookup"><span data-stu-id="99794-129">In the following example, a type in a module has an intrinsic type extension.</span></span> <span data-ttu-id="99794-130">外部模块的客户端代码，类型扩展将显示为在所有方面的类型的常规成员。</span><span class="sxs-lookup"><span data-stu-id="99794-130">To client code outside the module, the type extension appears as a regular member of the type in all respects.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3701.fs)]

<span data-ttu-id="99794-131">内部类型扩展可用于分隔成不同的部分类型的定义。</span><span class="sxs-lookup"><span data-stu-id="99794-131">You can use intrinsic type extensions to separate the definition of a type into sections.</span></span> <span data-ttu-id="99794-132">这可以是用于管理大型类型定义，例如，保持编译器生成的代码和编写的代码单独或组合在一起创建的不同的人或不同的功能与关联的代码。</span><span class="sxs-lookup"><span data-stu-id="99794-132">This can be useful in managing large type definitions, for example, to keep compiler-generated code and authored code separate or to group together code created by different people or associated with different functionality.</span></span>

<span data-ttu-id="99794-133">在下面的示例中，可选类型扩展将扩展`System.Int32`类型的扩展方法与`FromString`调用静态成员`Parse`。</span><span class="sxs-lookup"><span data-stu-id="99794-133">In the following example, an optional type extension extends the `System.Int32` type with an extension method `FromString` that calls the static member `Parse`.</span></span> <span data-ttu-id="99794-134">`testFromString`方法演示新成员称为就像任何实例成员一样。</span><span class="sxs-lookup"><span data-stu-id="99794-134">The `testFromString` method demonstrates that the new member is called just like any instance member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3702.fs)]

<span data-ttu-id="99794-135">新的实例成员将出现的任何其他方法一样`Int32`类型在 IntelliSense 中，而只包含扩展模块作用域中是打开或以其他方式。</span><span class="sxs-lookup"><span data-stu-id="99794-135">The new instance member will appear like any other method of the `Int32` type in IntelliSense, but only when the module that contains the extension is open or otherwise in scope.</span></span>

## <a name="generic-extension-methods"></a><span data-ttu-id="99794-136">泛型扩展方法</span><span class="sxs-lookup"><span data-stu-id="99794-136">Generic Extension Methods</span></span>
<span data-ttu-id="99794-137">在 F # 3.1 之前, 的 F # 编译器不支持使用 C# 的样式与泛型类型变量、 数组类型、 元组类型或 F # 函数类型作为"this"参数的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="99794-137">Before F# 3.1, the F# compiler didn't support the use of C#-style extension methods with a generic type variable, array type, tuple type, or an F# function type as the "this" parameter.</span></span> <span data-ttu-id="99794-138">F # 3.1 支持这些扩展成员使用。</span><span class="sxs-lookup"><span data-stu-id="99794-138">F# 3.1 supports the use of these extension members.</span></span>

<span data-ttu-id="99794-139">例如，在 F # 3.1 代码中，你可以使用与类似于以下语法在 C# 中的签名的扩展方法：</span><span class="sxs-lookup"><span data-stu-id="99794-139">For example, in F# 3.1 code, you can use extension methods with signatures that resemble the following syntax in C#:</span></span>

```csharp
static member Method<T>(this T input, T other)
```

<span data-ttu-id="99794-140">约束的泛型类型参数时，这种方法是特别有用。</span><span class="sxs-lookup"><span data-stu-id="99794-140">This approach is particularly useful when the generic type parameter is constrained.</span></span> <span data-ttu-id="99794-141">此外，你现在可以声明如下 F # 代码中的扩展成员并定义其他的、 在语义上丰富的一组扩展方法。</span><span class="sxs-lookup"><span data-stu-id="99794-141">Further, you can now declare extension members like this in F# code and define an additional, semantically rich set of extension methods.</span></span> <span data-ttu-id="99794-142">在 F # 中，你通常扩展成员定义如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="99794-142">In F#, you usually define extension members as the following example shows:</span></span>

```fsharp
open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq { for x in xs do for i in 1 .. n do yield x }
```

<span data-ttu-id="99794-143">但是，对于泛型类型，类型变量可能不受到约束。</span><span class="sxs-lookup"><span data-stu-id="99794-143">However, for a generic type, the type variable may not be constrained.</span></span> <span data-ttu-id="99794-144">你现在可以声明一个 C# 的 F # 若要解决此限制中的样式扩展成员。</span><span class="sxs-lookup"><span data-stu-id="99794-144">You can now declare a C#-style extension member in F# to work around this limitation.</span></span> <span data-ttu-id="99794-145">在你合并此类声明使用 F # 的内联功能，你可以作为扩展成员呈现泛型算法。</span><span class="sxs-lookup"><span data-stu-id="99794-145">When you combine this kind of declaration with the inline feature of F#, you can present generic algorithms as extension members.</span></span>

<span data-ttu-id="99794-146">请考虑以下声明：</span><span class="sxs-lookup"><span data-stu-id="99794-146">Consider the following declaration:</span></span>

```fsharp
[<Extension>]
type ExtraCSharpStyleExtensionMethodsInFSharp () =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="99794-147">通过使用此声明，可以编写类似于下面的示例代码。</span><span class="sxs-lookup"><span data-stu-id="99794-147">By using this declaration, you can write code that resembles the following sample.</span></span>

```fsharp
let listOfIntegers = [ 1 .. 100 ]
let listOfBigIntegers = [ 1I to 100I ]
let sum1 = listOfIntegers.Sum()
let sum2 = listOfBigIntegers.Sum()
```

<span data-ttu-id="99794-148">在此代码中，相同的泛型算术代码应用于两个类型的列表的如果没有重载，通过定义单个的扩展成员。</span><span class="sxs-lookup"><span data-stu-id="99794-148">In this code, the same generic arithmetic code is applied to lists of two types without overloading, by defining a single extension member.</span></span>


## <a name="see-also"></a><span data-ttu-id="99794-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99794-149">See Also</span></span>
[<span data-ttu-id="99794-150">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="99794-150">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="99794-151">成员</span><span class="sxs-lookup"><span data-stu-id="99794-151">Members</span></span>](members/index.md)
