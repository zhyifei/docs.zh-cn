---
title: 命名空间
description: 了解如何F#命名空间，可将代码组织到相关的功能区域，通过它可以将名称附加到的程序元素分组。
ms.date: 12/08/2018
ms.openlocfilehash: 526d7a07e4804751811c15fa91b0c74c1954d591
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613435"
---
# <a name="namespaces"></a><span data-ttu-id="af309-103">命名空间</span><span class="sxs-lookup"><span data-stu-id="af309-103">Namespaces</span></span>

<span data-ttu-id="af309-104">命名空间，可以将代码组织到相关的功能区域，通过它可以将名称附加一组F#的程序元素。</span><span class="sxs-lookup"><span data-stu-id="af309-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of F# program elements.</span></span> <span data-ttu-id="af309-105">命名空间是在通常顶级元素F#文件。</span><span class="sxs-lookup"><span data-stu-id="af309-105">Namespaces are typically top-level elements in F# files.</span></span>

## <a name="syntax"></a><span data-ttu-id="af309-106">语法</span><span class="sxs-lookup"><span data-stu-id="af309-106">Syntax</span></span>

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="af309-107">备注</span><span class="sxs-lookup"><span data-stu-id="af309-107">Remarks</span></span>

<span data-ttu-id="af309-108">如果你想要将代码放入一个命名空间，文件中的第一个声明必须声明命名空间。</span><span class="sxs-lookup"><span data-stu-id="af309-108">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="af309-109">然后将整个文件的内容会成为该命名空间的一部分，提供任何其他命名空间声明不存在更多的文件中。</span><span class="sxs-lookup"><span data-stu-id="af309-109">The contents of the entire file then become part of the namespace, provided no other namespaces declaration exists further in the file.</span></span> <span data-ttu-id="af309-110">如果是这种情况，然后被视为下一步的命名空间声明之前的所有代码可在第一个命名空间中。</span><span class="sxs-lookup"><span data-stu-id="af309-110">If that is the case, then all code up until the next namespace declaration is considered to be within the first namespace.</span></span>

<span data-ttu-id="af309-111">命名空间不能直接包含的值和函数。</span><span class="sxs-lookup"><span data-stu-id="af309-111">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="af309-112">相反，必须在模块中，包含值和函数以及模块包含命名空间中。</span><span class="sxs-lookup"><span data-stu-id="af309-112">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="af309-113">命名空间可以包含类型和模块。</span><span class="sxs-lookup"><span data-stu-id="af309-113">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="af309-114">XML 文档注释可以声明一个命名空间，上面，但它们将被忽略。</span><span class="sxs-lookup"><span data-stu-id="af309-114">XML doc comments can be declared above a namespace, but they're ignored.</span></span> <span data-ttu-id="af309-115">编译器指令还可以上述命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="af309-115">Compiler directives can also be declared above a namespace.</span></span>

<span data-ttu-id="af309-116">命名空间可以显式声明命名空间关键字，或隐式声明模块时。</span><span class="sxs-lookup"><span data-stu-id="af309-116">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="af309-117">若要显式声明命名空间，请使用命名空间关键字后跟的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="af309-117">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="af309-118">下面的示例演示声明一个命名空间的代码文件`Widgets`的类型和该命名空间中提供的模块。</span><span class="sxs-lookup"><span data-stu-id="af309-118">The following example shows a code file that declares a namespace `Widgets` with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="af309-119">如果该文件的全部内容都位于一个模块，还可以声明命名空间隐式使用`module`关键字并提供完全限定的模块名称中的新命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="af309-119">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="af309-120">下面的示例演示一个文件，其中声明一个命名空间`Widgets`和模块`WidgetsModule`，其中包含一个函数。</span><span class="sxs-lookup"><span data-stu-id="af309-120">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="af309-121">下面的代码是等效于上述代码中，但该模块是一个本地模块声明。</span><span class="sxs-lookup"><span data-stu-id="af309-121">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="af309-122">在这种情况下，命名空间必须出现在各自的行。</span><span class="sxs-lookup"><span data-stu-id="af309-122">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="af309-123">如果在同一文件中一个或多个命名空间中需要多个模块，则必须使用本地模块声明。</span><span class="sxs-lookup"><span data-stu-id="af309-123">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="af309-124">当使用本地模块声明时，不能在模块声明中使用的限定命名空间。</span><span class="sxs-lookup"><span data-stu-id="af309-124">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="af309-125">下面的代码显示了具有命名空间声明和两个本地模块声明的文件。</span><span class="sxs-lookup"><span data-stu-id="af309-125">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="af309-126">在这种情况下，这些模块直接包含在该命名空间。没有任何文件具有相同名称的隐式创建的模块。</span><span class="sxs-lookup"><span data-stu-id="af309-126">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="af309-127">任何其他代码在文件中，如`do`绑定，因此需要限定模块成员位于命名空间中但不是在的内部模块`widgetFunction`通过使用模块名称。</span><span class="sxs-lookup"><span data-stu-id="af309-127">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="af309-128">此示例的输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="af309-128">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="af309-129">有关详细信息，请参阅[模块](modules.md)。</span><span class="sxs-lookup"><span data-stu-id="af309-129">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="af309-130">嵌套的命名空间</span><span class="sxs-lookup"><span data-stu-id="af309-130">Nested Namespaces</span></span>

<span data-ttu-id="af309-131">在创建嵌套的命名空间时，必须完全限定它。</span><span class="sxs-lookup"><span data-stu-id="af309-131">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="af309-132">否则，您创建新的顶级命名空间。</span><span class="sxs-lookup"><span data-stu-id="af309-132">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="af309-133">命名空间声明中将忽略缩进。</span><span class="sxs-lookup"><span data-stu-id="af309-133">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="af309-134">下面的示例演示如何声明嵌套的命名空间。</span><span class="sxs-lookup"><span data-stu-id="af309-134">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="af309-135">中的文件和程序集的命名空间</span><span class="sxs-lookup"><span data-stu-id="af309-135">Namespaces in Files and Assemblies</span></span>

<span data-ttu-id="af309-136">命名空间可以跨多个文件中的单个项目或编译。</span><span class="sxs-lookup"><span data-stu-id="af309-136">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="af309-137">术语*命名空间片段*介绍包含在一个文件中的命名空间的一部分。</span><span class="sxs-lookup"><span data-stu-id="af309-137">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="af309-138">命名空间还可以跨多个程序集。</span><span class="sxs-lookup"><span data-stu-id="af309-138">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="af309-139">例如，`System`命名空间中包含整个.NET Framework，也不能跨越多个程序集包含多个嵌套的命名空间。</span><span class="sxs-lookup"><span data-stu-id="af309-139">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>

## <a name="global-namespace"></a><span data-ttu-id="af309-140">全局 Namespace</span><span class="sxs-lookup"><span data-stu-id="af309-140">Global Namespace</span></span>

<span data-ttu-id="af309-141">使用预定义的命名空间`global`将名称放在.NET 顶级命名空间。</span><span class="sxs-lookup"><span data-stu-id="af309-141">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="af309-142">您还可以使用全局若要引用的顶级的.NET 命名空间，例如，若要解决与其他命名空间的名称冲突。</span><span class="sxs-lookup"><span data-stu-id="af309-142">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="af309-143">递归命名空间</span><span class="sxs-lookup"><span data-stu-id="af309-143">Recursive namespaces</span></span>

<span data-ttu-id="af309-144">此外可以为递归，从而允许所有包含的代码要相互递归声明命名空间。</span><span class="sxs-lookup"><span data-stu-id="af309-144">Namespaces can also be declared as recursive to allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="af309-145">这是通过`namespace rec`。</span><span class="sxs-lookup"><span data-stu-id="af309-145">This is done via `namespace rec`.</span></span> <span data-ttu-id="af309-146">使用`namespace rec`可以缓解一些烦恼无法编写类型和模块之间相互引用代码中的。</span><span class="sxs-lookup"><span data-stu-id="af309-146">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span> <span data-ttu-id="af309-147">以下是此示例：</span><span class="sxs-lookup"><span data-stu-id="af309-147">The following is an example of this:</span></span>

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

type BananaPeel() = class end

type Banana(orientation : Orientation) =
    member val IsPeeled = false with get, set
    member val Orientation = orientation with get, set
    member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set

    member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
    member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

module BananaHelpers =
    let peel (b: Banana) =
        let flip (banana: Banana) =
            match banana.Orientation with
            | Up -> 
                banana.Orientation <- Down
                banana
            | Down -> banana

        let peelSides (banana: Banana) =
            banana.Sides
            |> List.map (function
                         | Unpeeled -> Peeled
                         | Peeled -> Peeled)

        match b.Orientation with
        | Up ->   b |> flip |> peelSides
        | Down -> b |> peelSides
```

<span data-ttu-id="af309-148">请注意，异常`DontSqueezeTheBananaException`和类`Banana`两者相互引用。</span><span class="sxs-lookup"><span data-stu-id="af309-148">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="af309-149">此外，模块`BananaHelpers`和类`Banana`也相互引用。</span><span class="sxs-lookup"><span data-stu-id="af309-149">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span> <span data-ttu-id="af309-150">这不是可能表示F#如果你删除`rec`关键字从`MutualReferences`命名空间。</span><span class="sxs-lookup"><span data-stu-id="af309-150">This wouldn't be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="af309-151">此功能也仅适用于顶级[模块](modules.md)。</span><span class="sxs-lookup"><span data-stu-id="af309-151">This feature is also available for top-level [Modules](modules.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="af309-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="af309-152">See also</span></span>

- [<span data-ttu-id="af309-153">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="af309-153">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="af309-154">模块</span><span class="sxs-lookup"><span data-stu-id="af309-154">Modules</span></span>](modules.md)
- [<span data-ttu-id="af309-155">F#RFC FS-1009-允许通过在文件中的较大范围的相互引用类型和模块</span><span class="sxs-lookup"><span data-stu-id="af309-155">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)