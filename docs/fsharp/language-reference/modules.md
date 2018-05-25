---
title: 模块 (F#)
description: '了解如何 F # 模块是 F # 代码，例如值、 类型和函数值，F # 程序中的分组。'
ms.date: 04/24/2017
ms.openlocfilehash: 9a1416321e392f7a06551b4a7e3429e3a2d023bd
ms.sourcegitcommit: b7763f3435635850a76d4cbcf09bdce6c019208a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2018
---
# <a name="modules"></a><span data-ttu-id="c3e21-103">模块</span><span class="sxs-lookup"><span data-stu-id="c3e21-103">Modules</span></span>

<span data-ttu-id="c3e21-104">F # 语言的上下文中*模块*是 F # 代码，例如值、 类型和函数值，F # 程序中的分组。</span><span class="sxs-lookup"><span data-stu-id="c3e21-104">In the context of the F# language, a *module* is a grouping of F# code, such as values, types, and function values, in an F# program.</span></span> <span data-ttu-id="c3e21-105">对模块中的代码进行分组有助于将相关代码放在一起，并有助于避免程序中的名称冲突。</span><span class="sxs-lookup"><span data-stu-id="c3e21-105">Grouping code in modules helps keep related code together and helps avoid name conflicts in your program.</span></span>

## <a name="syntax"></a><span data-ttu-id="c3e21-106">语法</span><span class="sxs-lookup"><span data-stu-id="c3e21-106">Syntax</span></span>

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a><span data-ttu-id="c3e21-107">备注</span><span class="sxs-lookup"><span data-stu-id="c3e21-107">Remarks</span></span>
<span data-ttu-id="c3e21-108">F # 模块是分组，如类型、 值、 函数值和中的代码的 F # 代码构造的`do`绑定。</span><span class="sxs-lookup"><span data-stu-id="c3e21-108">An F# module is a grouping of F# code constructs such as types, values, function values, and code in `do` bindings.</span></span> <span data-ttu-id="c3e21-109">它只包含静态成员的公共语言运行时 (CLR) 类作为实现。</span><span class="sxs-lookup"><span data-stu-id="c3e21-109">It is implemented as a common language runtime (CLR) class that has only static members.</span></span> <span data-ttu-id="c3e21-110">有两种类型的模块声明，具体取决于该模块中是否包含整个文件： 顶级模块声明和本地模块声明。</span><span class="sxs-lookup"><span data-stu-id="c3e21-110">There are two types of module declarations, depending on whether the whole file is included in the module: a top-level module declaration and a local module declaration.</span></span> <span data-ttu-id="c3e21-111">顶级模块声明的模块中包括整个文件。</span><span class="sxs-lookup"><span data-stu-id="c3e21-111">A top-level module declaration includes the whole file in the module.</span></span> <span data-ttu-id="c3e21-112">顶级模块声明可以显示仅为一个文件中的第一个声明。</span><span class="sxs-lookup"><span data-stu-id="c3e21-112">A top-level module declaration can appear only as the first declaration in a file.</span></span>

<span data-ttu-id="c3e21-113">可选的顶级模块声明的语法中*限定命名空间*是包含该模块的序列的嵌套命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="c3e21-113">In the syntax for the top-level module declaration, the optional *qualified-namespace* is the sequence of nested namespace names that contains the module.</span></span> <span data-ttu-id="c3e21-114">限定的命名空间没有以前声明。</span><span class="sxs-lookup"><span data-stu-id="c3e21-114">The qualified namespace does not have to be previously declared.</span></span>

<span data-ttu-id="c3e21-115">无需缩进顶级模块中的声明。</span><span class="sxs-lookup"><span data-stu-id="c3e21-115">You do not have to indent declarations in a top-level module.</span></span> <span data-ttu-id="c3e21-116">你不必要缩进本地模块中的所有声明。</span><span class="sxs-lookup"><span data-stu-id="c3e21-116">You do have to indent all declarations in local modules.</span></span> <span data-ttu-id="c3e21-117">在本地模块声明中，仅将该模块声明之下缩进的声明是模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="c3e21-117">In a local module declaration, only the declarations that are indented under that module declaration are part of the module.</span></span>

<span data-ttu-id="c3e21-118">如果代码文件不以开头的顶级模块声明或命名空间声明中，整个文件的内容，包括任何本地模块，将成为文件，而不进行扩展，与具有相同名称的隐式创建顶级模块的一部分与第一个字母转换为大写形式。</span><span class="sxs-lookup"><span data-stu-id="c3e21-118">If a code file does not begin with a top-level module declaration or a namespace declaration, the whole contents of the file, including any local modules, becomes part of an implicitly created top-level module that has the same name as the file, without the extension, with the first letter converted to uppercase.</span></span> <span data-ttu-id="c3e21-119">例如，考虑下面的文件。</span><span class="sxs-lookup"><span data-stu-id="c3e21-119">For example, consider the following file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6601.fs)]

<span data-ttu-id="c3e21-120">此文件将进行编译，就像这种方式编写：</span><span class="sxs-lookup"><span data-stu-id="c3e21-120">This file would be compiled as if it were written in this manner:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6602.fs)]

<span data-ttu-id="c3e21-121">如果你有多个模块文件中，你必须为每个模块使用本地模块声明。</span><span class="sxs-lookup"><span data-stu-id="c3e21-121">If you have multiple modules in a file, you must use a local module declaration for each module.</span></span> <span data-ttu-id="c3e21-122">如果声明为外层命名空间，这些模块是封闭命名空间的一部分。</span><span class="sxs-lookup"><span data-stu-id="c3e21-122">If an enclosing namespace is declared, these modules are part of the enclosing namespace.</span></span> <span data-ttu-id="c3e21-123">如果不声明外层命名空间，模块将成为隐式创建的顶级模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="c3e21-123">If an enclosing namespace is not declared, the modules become part of the implicitly created top-level module.</span></span> <span data-ttu-id="c3e21-124">下面的代码示例显示包含多个模块的代码文件。</span><span class="sxs-lookup"><span data-stu-id="c3e21-124">The following code example shows a code file that contains multiple modules.</span></span> <span data-ttu-id="c3e21-125">编译器隐式创建一个名为的顶级模块`Multiplemodules`，和`MyModule1`和`MyModule2`嵌套在该顶级模块。</span><span class="sxs-lookup"><span data-stu-id="c3e21-125">The compiler implicitly creates a top-level module named `Multiplemodules`, and `MyModule1` and `MyModule2` are nested in that top-level module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6603.fs)]

<span data-ttu-id="c3e21-126">如果你有多个文件的项目中或在单个编译中，或如果你要构建库，则必须包含命名空间声明或模块文件顶部的声明。</span><span class="sxs-lookup"><span data-stu-id="c3e21-126">If you have multiple files in a project or in a single compilation, or if you are building a library, you must include a namespace declaration or module declaration at the top of the file.</span></span> <span data-ttu-id="c3e21-127">F # 编译器仅确定模块名称隐式当在项目或编译命令行中，只有一个文件并且你要创建的应用。</span><span class="sxs-lookup"><span data-stu-id="c3e21-127">The F# compiler only determines a module name implicitly when there is only one file in a project or compilation command line, and you are creating an application.</span></span>

<span data-ttu-id="c3e21-128">*可访问性修饰符*可以是以下之一： `public`， `private`， `internal`。</span><span class="sxs-lookup"><span data-stu-id="c3e21-128">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="c3e21-129">有关详细信息，请参阅[访问控制](access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="c3e21-129">For more information, see [Access Control](access-control.md).</span></span> <span data-ttu-id="c3e21-130">默认值为 public。</span><span class="sxs-lookup"><span data-stu-id="c3e21-130">The default is public.</span></span>


## <a name="referencing-code-in-modules"></a><span data-ttu-id="c3e21-131">引用的模块中的代码</span><span class="sxs-lookup"><span data-stu-id="c3e21-131">Referencing Code in Modules</span></span>
<span data-ttu-id="c3e21-132">在从另一个模块引用函数、 类型和值时，你必须使用限定的名称或打开该模块。</span><span class="sxs-lookup"><span data-stu-id="c3e21-132">When you reference functions, types, and values from another module, you must either use a qualified name or open the module.</span></span> <span data-ttu-id="c3e21-133">如果你使用的限定的名称，则必须指定命名空间、 模块和所需的程序元素的标识符。</span><span class="sxs-lookup"><span data-stu-id="c3e21-133">If you use a qualified name, you must specify the namespaces, the module, and the identifier for the program element you want.</span></span> <span data-ttu-id="c3e21-134">如下所示带有圆点 （.） 分隔每个部分限定的路径。</span><span class="sxs-lookup"><span data-stu-id="c3e21-134">You separate each part of the qualified path with a dot (.), as follows.</span></span>

`Namespace1.Namespace2.ModuleName.Identifier`

<span data-ttu-id="c3e21-135">你可以打开该模块或一个或多个要简化代码的命名空间。</span><span class="sxs-lookup"><span data-stu-id="c3e21-135">You can open the module or one or more of the namespaces to simplify the code.</span></span> <span data-ttu-id="c3e21-136">有关打开命名空间和模块的详细信息，请参阅[导入声明：`open`关键字](import-declarations-the-open-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="c3e21-136">For more information about opening namespaces and modules, see [Import Declarations: The `open` Keyword](import-declarations-the-open-keyword.md).</span></span>

<span data-ttu-id="c3e21-137">下面的代码示例显示一个包含最多文件末尾的所有代码的顶级模块。</span><span class="sxs-lookup"><span data-stu-id="c3e21-137">The following code example shows a top-level module that contains all the code up to the end of the file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6604.fs)]

<span data-ttu-id="c3e21-138">若要从同一项目中的另一个文件中使用此代码，你使用限定的名称或打开该模块，然后使用这些函数，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="c3e21-138">To use this code from another file in the same project, you either use qualified names or you open the module before you use the functions, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a><span data-ttu-id="c3e21-139">嵌套的模块</span><span class="sxs-lookup"><span data-stu-id="c3e21-139">Nested Modules</span></span>
<span data-ttu-id="c3e21-140">可以嵌套模块。</span><span class="sxs-lookup"><span data-stu-id="c3e21-140">Modules can be nested.</span></span> <span data-ttu-id="c3e21-141">内部模块必须与外部模块声明，以指示它们是内部模块，而不是新模块缩进。</span><span class="sxs-lookup"><span data-stu-id="c3e21-141">Inner modules must be indented as far as outer module declarations to indicate that they are inner modules, not new modules.</span></span> <span data-ttu-id="c3e21-142">例如，比较下面两个示例。</span><span class="sxs-lookup"><span data-stu-id="c3e21-142">For example, compare the following two examples.</span></span> <span data-ttu-id="c3e21-143">模块`Z`是下面的代码中一个内部模块。</span><span class="sxs-lookup"><span data-stu-id="c3e21-143">Module `Z` is an inner module in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6607.fs)]

<span data-ttu-id="c3e21-144">但模块`Z`是模块同级`Y`下面的代码中。</span><span class="sxs-lookup"><span data-stu-id="c3e21-144">But module `Z` is a sibling to module `Y` in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6608.fs)]
<span data-ttu-id="c3e21-145">模块`Z`也是在以下代码中，是同级模块，因为它不会与其他模块中声明缩进`Y`。</span><span class="sxs-lookup"><span data-stu-id="c3e21-145">Module `Z` is also a sibling module in the following code, because it is not indented as far as other declarations in module `Y`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6609.fs)]
<span data-ttu-id="c3e21-146">最后，如果外部模块不包含任何声明，并且立即跟另一个模块声明，新的模块声明被假定为一个内部模块，但编译器会警告你如果第二个模块定义不会缩进 farther 比第一个。</span><span class="sxs-lookup"><span data-stu-id="c3e21-146">Finally, if the outer module has no declarations and is followed immediately by another module declaration, the new module declaration is assumed to be an inner module, but the compiler will warn you if the second module definition is not indented farther than the first.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6610.fs)]
<span data-ttu-id="c3e21-147">若要消除此警告，缩进的内部模块。</span><span class="sxs-lookup"><span data-stu-id="c3e21-147">To eliminate the warning, indent the inner module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6611.fs)]
<span data-ttu-id="c3e21-148">如果你想要在单个外部模块中的文件中的所有代码，你都需要使用内部模块外部模块不需要在等号和声明，包括任何内部模块声明，会在外部模块中无需进行缩进。</span><span class="sxs-lookup"><span data-stu-id="c3e21-148">If you want all the code in a file to be in a single outer module and you want inner modules, the outer module does not require the equal sign, and the declarations, including any inner module declarations, that will go in the outer module do not have to be indented.</span></span> <span data-ttu-id="c3e21-149">在内部模块声明的声明必须存在要缩进。</span><span class="sxs-lookup"><span data-stu-id="c3e21-149">Declarations inside the inner module declarations do have to be indented.</span></span> <span data-ttu-id="c3e21-150">下面的代码演示了这种情况。</span><span class="sxs-lookup"><span data-stu-id="c3e21-150">The following code shows this case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a><span data-ttu-id="c3e21-151">递归模块</span><span class="sxs-lookup"><span data-stu-id="c3e21-151">Recursive modules</span></span>

<span data-ttu-id="c3e21-152">F # 4.1 引入了允许的所有包含的代码要相互递归的模块的概念。</span><span class="sxs-lookup"><span data-stu-id="c3e21-152">F# 4.1 introduces the notion of modules which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="c3e21-153">这是通过`module rec`。</span><span class="sxs-lookup"><span data-stu-id="c3e21-153">This is done via `module rec`.</span></span>  <span data-ttu-id="c3e21-154">利用`module rec`可以减轻中无法编写类型和模块之间的相互引用代码的一些难题。</span><span class="sxs-lookup"><span data-stu-id="c3e21-154">Use of `module rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="c3e21-155">下面是此示例：</span><span class="sxs-lookup"><span data-stu-id="c3e21-155">The following is an example of this:</span></span>

```fsharp
module rec RecursiveModule =
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

<span data-ttu-id="c3e21-156">请注意，异常`DontSqueezeTheBananaException`和类`Banana`同时相互引用。</span><span class="sxs-lookup"><span data-stu-id="c3e21-156">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="c3e21-157">此外，该模块`BananaHelpers`和类`Banana`也相互引用。</span><span class="sxs-lookup"><span data-stu-id="c3e21-157">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="c3e21-158">这将不可能表示在 F # 中，如果你删除`rec`关键字从`RecursiveModule`模块。</span><span class="sxs-lookup"><span data-stu-id="c3e21-158">This would not be possible to express in F# if you removed the `rec` keyword from the `RecursiveModule` module.</span></span>

<span data-ttu-id="c3e21-159">此功能，还可以在[命名空间](namespaces.md)F # 4.1。</span><span class="sxs-lookup"><span data-stu-id="c3e21-159">This capability is also possible in [Namespaces](namespaces.md) with F# 4.1.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3e21-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3e21-160">See also</span></span>

[<span data-ttu-id="c3e21-161">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="c3e21-161">F# Language Reference</span></span>](index.md)  
[<span data-ttu-id="c3e21-162">命名空间</span><span class="sxs-lookup"><span data-stu-id="c3e21-162">Namespaces</span></span>](namespaces.md)  
[<span data-ttu-id="c3e21-163">F # RFC FS-1009-允许通过在文件内的较大作用域的互相引用的类型和模块</span><span class="sxs-lookup"><span data-stu-id="c3e21-163">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)  
