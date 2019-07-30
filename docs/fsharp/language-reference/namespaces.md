---
title: 命名空间
description: 了解F#命名空间如何允许用户将名称附加到一组程序元素, 从而将代码组织到相关功能的各个区域。
ms.date: 12/08/2018
ms.openlocfilehash: d295f25cae81bc28b4fcb522bdcacde862f9517a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627373"
---
# <a name="namespaces"></a><span data-ttu-id="f67b0-103">命名空间</span><span class="sxs-lookup"><span data-stu-id="f67b0-103">Namespaces</span></span>

<span data-ttu-id="f67b0-104">命名空间使你能够将一个名称附加到一组F#程序元素, 从而将代码组织到相关功能的各个区域。</span><span class="sxs-lookup"><span data-stu-id="f67b0-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of F# program elements.</span></span> <span data-ttu-id="f67b0-105">命名空间通常是文件中F#的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="f67b0-105">Namespaces are typically top-level elements in F# files.</span></span>

## <a name="syntax"></a><span data-ttu-id="f67b0-106">语法</span><span class="sxs-lookup"><span data-stu-id="f67b0-106">Syntax</span></span>

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="f67b0-107">备注</span><span class="sxs-lookup"><span data-stu-id="f67b0-107">Remarks</span></span>

<span data-ttu-id="f67b0-108">如果要将代码放入命名空间中, 则文件中的第一个声明必须声明命名空间。</span><span class="sxs-lookup"><span data-stu-id="f67b0-108">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="f67b0-109">如果文件中不存在其他命名空间声明, 则整个文件的内容将成为命名空间的一部分。</span><span class="sxs-lookup"><span data-stu-id="f67b0-109">The contents of the entire file then become part of the namespace, provided no other namespaces declaration exists further in the file.</span></span> <span data-ttu-id="f67b0-110">如果是这种情况, 则所有代码直到下一个命名空间声明都被视为位于第一个命名空间内。</span><span class="sxs-lookup"><span data-stu-id="f67b0-110">If that is the case, then all code up until the next namespace declaration is considered to be within the first namespace.</span></span>

<span data-ttu-id="f67b0-111">命名空间不能直接包含值和函数。</span><span class="sxs-lookup"><span data-stu-id="f67b0-111">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="f67b0-112">相反, 值和函数必须包含在模块中, 且模块包含在命名空间中。</span><span class="sxs-lookup"><span data-stu-id="f67b0-112">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="f67b0-113">命名空间可以包含类型和模块。</span><span class="sxs-lookup"><span data-stu-id="f67b0-113">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="f67b0-114">XML 文档注释可以在命名空间之上声明, 但会被忽略。</span><span class="sxs-lookup"><span data-stu-id="f67b0-114">XML doc comments can be declared above a namespace, but they're ignored.</span></span> <span data-ttu-id="f67b0-115">还可以在命名空间之上声明编译器指令。</span><span class="sxs-lookup"><span data-stu-id="f67b0-115">Compiler directives can also be declared above a namespace.</span></span>

<span data-ttu-id="f67b0-116">可以使用 namespace 关键字显式声明命名空间, 或在声明模块时隐式声明命名空间。</span><span class="sxs-lookup"><span data-stu-id="f67b0-116">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="f67b0-117">若要显式声明命名空间, 请使用 namespace 关键字, 后跟命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="f67b0-117">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="f67b0-118">下面的示例演示一个代码文件, 该代码文件`Widgets`声明具有类型的命名空间和包含在该命名空间中的模块。</span><span class="sxs-lookup"><span data-stu-id="f67b0-118">The following example shows a code file that declares a namespace `Widgets` with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="f67b0-119">如果该文件的所有内容都在一个模块中, 则还可以使用`module`关键字隐式声明命名空间, 并在完全限定的模块名称中提供新的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="f67b0-119">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="f67b0-120">下面的示例演示一个声明命名空间`Widgets`的代码文件和一个包含函数的模块。 `WidgetsModule`</span><span class="sxs-lookup"><span data-stu-id="f67b0-120">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="f67b0-121">下面的代码等效于前面的代码, 但模块为本地模块声明。</span><span class="sxs-lookup"><span data-stu-id="f67b0-121">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="f67b0-122">在这种情况下, 命名空间必须出现在其自己的行上。</span><span class="sxs-lookup"><span data-stu-id="f67b0-122">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="f67b0-123">如果一个或多个命名空间中的同一文件中需要多个模块, 则必须使用本地模块声明。</span><span class="sxs-lookup"><span data-stu-id="f67b0-123">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="f67b0-124">使用本地模块声明时, 不能在模块声明中使用限定的命名空间。</span><span class="sxs-lookup"><span data-stu-id="f67b0-124">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="f67b0-125">下面的代码演示一个具有命名空间声明和两个本地模块声明的文件。</span><span class="sxs-lookup"><span data-stu-id="f67b0-125">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="f67b0-126">在这种情况下, 模块直接包含在命名空间中;没有隐式创建的与该文件同名的模块。</span><span class="sxs-lookup"><span data-stu-id="f67b0-126">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="f67b0-127">文件中的任何其他代码 (如`do`绑定) 都位于命名空间中, 但不在内部模块中, 因此需要使用模块名称来限定模块成员。 `widgetFunction`</span><span class="sxs-lookup"><span data-stu-id="f67b0-127">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="f67b0-128">此示例的输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="f67b0-128">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="f67b0-129">有关详细信息, 请参阅[模块](modules.md)。</span><span class="sxs-lookup"><span data-stu-id="f67b0-129">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="f67b0-130">嵌套命名空间</span><span class="sxs-lookup"><span data-stu-id="f67b0-130">Nested Namespaces</span></span>

<span data-ttu-id="f67b0-131">创建嵌套命名空间时, 必须完全限定该命名空间。</span><span class="sxs-lookup"><span data-stu-id="f67b0-131">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="f67b0-132">否则, 将创建一个新的顶级命名空间。</span><span class="sxs-lookup"><span data-stu-id="f67b0-132">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="f67b0-133">命名空间声明中将忽略缩进。</span><span class="sxs-lookup"><span data-stu-id="f67b0-133">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="f67b0-134">下面的示例演示如何声明嵌套命名空间。</span><span class="sxs-lookup"><span data-stu-id="f67b0-134">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="f67b0-135">文件和程序集中的命名空间</span><span class="sxs-lookup"><span data-stu-id="f67b0-135">Namespaces in Files and Assemblies</span></span>

<span data-ttu-id="f67b0-136">命名空间可跨单个项目或编译中的多个文件。</span><span class="sxs-lookup"><span data-stu-id="f67b0-136">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="f67b0-137">术语 "*命名空间片段*" 描述包含在一个文件中的命名空间的一部分。</span><span class="sxs-lookup"><span data-stu-id="f67b0-137">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="f67b0-138">命名空间也可以跨多个程序集。</span><span class="sxs-lookup"><span data-stu-id="f67b0-138">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="f67b0-139">例如, `System`命名空间包含整个 .NET Framework, 这跨多个程序集, 并且包含许多嵌套命名空间。</span><span class="sxs-lookup"><span data-stu-id="f67b0-139">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>

## <a name="global-namespace"></a><span data-ttu-id="f67b0-140">全局命名空间</span><span class="sxs-lookup"><span data-stu-id="f67b0-140">Global Namespace</span></span>

<span data-ttu-id="f67b0-141">使用预定义的命名`global`空间将名称放在 .net 顶级命名空间中。</span><span class="sxs-lookup"><span data-stu-id="f67b0-141">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="f67b0-142">你还可以使用 global 引用顶层 .NET 命名空间, 例如, 解析与其他命名空间的名称冲突。</span><span class="sxs-lookup"><span data-stu-id="f67b0-142">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="f67b0-143">递归命名空间</span><span class="sxs-lookup"><span data-stu-id="f67b0-143">Recursive namespaces</span></span>

<span data-ttu-id="f67b0-144">还可以将命名空间声明为 recursive, 以允许所有包含的代码相互递归。</span><span class="sxs-lookup"><span data-stu-id="f67b0-144">Namespaces can also be declared as recursive to allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="f67b0-145">这是通过`namespace rec`实现的。</span><span class="sxs-lookup"><span data-stu-id="f67b0-145">This is done via `namespace rec`.</span></span> <span data-ttu-id="f67b0-146">`namespace rec`使用可以减少无法在类型和模块之间编写相互引用代码的一些难题。</span><span class="sxs-lookup"><span data-stu-id="f67b0-146">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span> <span data-ttu-id="f67b0-147">下面是一个示例:</span><span class="sxs-lookup"><span data-stu-id="f67b0-147">The following is an example of this:</span></span>

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

<span data-ttu-id="f67b0-148">请注意, 异常`DontSqueezeTheBananaException`和类`Banana`都相互引用。</span><span class="sxs-lookup"><span data-stu-id="f67b0-148">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="f67b0-149">此外, 模块`BananaHelpers`和类`Banana`也相互引用。</span><span class="sxs-lookup"><span data-stu-id="f67b0-149">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span> <span data-ttu-id="f67b0-150">如果从F# `rec` 命名空间中删除关键字,则无法在中进行表示。`MutualReferences`</span><span class="sxs-lookup"><span data-stu-id="f67b0-150">This wouldn't be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="f67b0-151">此功能也适用于顶级[模块](modules.md)。</span><span class="sxs-lookup"><span data-stu-id="f67b0-151">This feature is also available for top-level [Modules](modules.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f67b0-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="f67b0-152">See also</span></span>

- [<span data-ttu-id="f67b0-153">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="f67b0-153">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="f67b0-154">模块</span><span class="sxs-lookup"><span data-stu-id="f67b0-154">Modules</span></span>](modules.md)
- [<span data-ttu-id="f67b0-155">F#RFC FS-1009-允许在文件中的更大范围内进行相互引用类型和模块</span><span class="sxs-lookup"><span data-stu-id="f67b0-155">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
