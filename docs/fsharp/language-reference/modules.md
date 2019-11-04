---
title: 模块
description: 了解F#模块是F# F#程序中的代码分组，如值、类型和函数值。
ms.date: 04/24/2017
ms.openlocfilehash: fbde0c8b001d88614ba2de49c4aa7bfa098c6945
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425057"
---
# <a name="modules"></a><span data-ttu-id="b0374-103">模块</span><span class="sxs-lookup"><span data-stu-id="b0374-103">Modules</span></span>

<span data-ttu-id="b0374-104">在该F#语言的上下文中，*模块*是F# F#程序中代码的分组，如值、类型和函数值。</span><span class="sxs-lookup"><span data-stu-id="b0374-104">In the context of the F# language, a *module* is a grouping of F# code, such as values, types, and function values, in an F# program.</span></span> <span data-ttu-id="b0374-105">对模块中的代码进行分组有助于将相关代码放在一起，并有助于避免程序中的名称冲突。</span><span class="sxs-lookup"><span data-stu-id="b0374-105">Grouping code in modules helps keep related code together and helps avoid name conflicts in your program.</span></span>

## <a name="syntax"></a><span data-ttu-id="b0374-106">语法</span><span class="sxs-lookup"><span data-stu-id="b0374-106">Syntax</span></span>

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a><span data-ttu-id="b0374-107">备注</span><span class="sxs-lookup"><span data-stu-id="b0374-107">Remarks</span></span>

<span data-ttu-id="b0374-108">F#模块是代码构造的F#分组，如类型、值、函数值和 `do` 绑定中的代码。</span><span class="sxs-lookup"><span data-stu-id="b0374-108">An F# module is a grouping of F# code constructs such as types, values, function values, and code in `do` bindings.</span></span> <span data-ttu-id="b0374-109">它实现为只有静态成员的公共语言运行时（CLR）类。</span><span class="sxs-lookup"><span data-stu-id="b0374-109">It is implemented as a common language runtime (CLR) class that has only static members.</span></span> <span data-ttu-id="b0374-110">模块声明有两种类型，具体取决于整个文件是否包含在模块中：顶级模块声明和局部模块声明。</span><span class="sxs-lookup"><span data-stu-id="b0374-110">There are two types of module declarations, depending on whether the whole file is included in the module: a top-level module declaration and a local module declaration.</span></span> <span data-ttu-id="b0374-111">顶级模块声明在模块中包含整个文件。</span><span class="sxs-lookup"><span data-stu-id="b0374-111">A top-level module declaration includes the whole file in the module.</span></span> <span data-ttu-id="b0374-112">顶级模块声明只能显示为文件中的第一个声明。</span><span class="sxs-lookup"><span data-stu-id="b0374-112">A top-level module declaration can appear only as the first declaration in a file.</span></span>

<span data-ttu-id="b0374-113">在顶级模块声明的语法中，可选的*限定命名空间*是包含模块的嵌套命名空间名称的序列。</span><span class="sxs-lookup"><span data-stu-id="b0374-113">In the syntax for the top-level module declaration, the optional *qualified-namespace* is the sequence of nested namespace names that contains the module.</span></span> <span data-ttu-id="b0374-114">不需要事先声明限定的命名空间。</span><span class="sxs-lookup"><span data-stu-id="b0374-114">The qualified namespace does not have to be previously declared.</span></span>

<span data-ttu-id="b0374-115">无需缩进顶级模块中的声明。</span><span class="sxs-lookup"><span data-stu-id="b0374-115">You do not have to indent declarations in a top-level module.</span></span> <span data-ttu-id="b0374-116">必须缩进本地模块中的所有声明。</span><span class="sxs-lookup"><span data-stu-id="b0374-116">You do have to indent all declarations in local modules.</span></span> <span data-ttu-id="b0374-117">在本地模块声明中，仅在该模块声明下缩进的声明是该模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="b0374-117">In a local module declaration, only the declarations that are indented under that module declaration are part of the module.</span></span>

<span data-ttu-id="b0374-118">如果代码文件不是以顶级模块声明或命名空间声明开头，则该文件的整个内容（包括任何本地模块）将成为隐式创建的顶级模块的一部分，该模块具有与文件相同的名称，但不包含扩展名。第一个字母转换为大写。</span><span class="sxs-lookup"><span data-stu-id="b0374-118">If a code file does not begin with a top-level module declaration or a namespace declaration, the whole contents of the file, including any local modules, becomes part of an implicitly created top-level module that has the same name as the file, without the extension, with the first letter converted to uppercase.</span></span> <span data-ttu-id="b0374-119">例如，请考虑以下文件。</span><span class="sxs-lookup"><span data-stu-id="b0374-119">For example, consider the following file.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6601.fs)]

<span data-ttu-id="b0374-120">此文件的编译方式如下：</span><span class="sxs-lookup"><span data-stu-id="b0374-120">This file would be compiled as if it were written in this manner:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6602.fs)]

<span data-ttu-id="b0374-121">如果文件中有多个模块，则必须对每个模块使用本地模块声明。</span><span class="sxs-lookup"><span data-stu-id="b0374-121">If you have multiple modules in a file, you must use a local module declaration for each module.</span></span> <span data-ttu-id="b0374-122">如果声明了封闭命名空间，则这些模块是封闭命名空间的一部分。</span><span class="sxs-lookup"><span data-stu-id="b0374-122">If an enclosing namespace is declared, these modules are part of the enclosing namespace.</span></span> <span data-ttu-id="b0374-123">如果未声明封闭命名空间，模块将成为隐式创建的顶级模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="b0374-123">If an enclosing namespace is not declared, the modules become part of the implicitly created top-level module.</span></span> <span data-ttu-id="b0374-124">下面的代码示例显示了一个包含多个模块的代码文件。</span><span class="sxs-lookup"><span data-stu-id="b0374-124">The following code example shows a code file that contains multiple modules.</span></span> <span data-ttu-id="b0374-125">编译器隐式创建一个名为 `Multiplemodules`的顶级模块，并且 `MyModule1` 并且 `MyModule2` 嵌套在该顶级模块中。</span><span class="sxs-lookup"><span data-stu-id="b0374-125">The compiler implicitly creates a top-level module named `Multiplemodules`, and `MyModule1` and `MyModule2` are nested in that top-level module.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6603.fs)]

<span data-ttu-id="b0374-126">如果在一个项目中或在单个编译中有多个文件，或者如果要生成一个库，则必须在该文件的顶部包含一个命名空间声明或模块声明。</span><span class="sxs-lookup"><span data-stu-id="b0374-126">If you have multiple files in a project or in a single compilation, or if you are building a library, you must include a namespace declaration or module declaration at the top of the file.</span></span> <span data-ttu-id="b0374-127">F#编译器仅在项目或编译命令行中只有一个文件，并且你正在创建应用程序时，才会隐式确定模块名称。</span><span class="sxs-lookup"><span data-stu-id="b0374-127">The F# compiler only determines a module name implicitly when there is only one file in a project or compilation command line, and you are creating an application.</span></span>

<span data-ttu-id="b0374-128">可*访问性修饰符*可以是以下项之一： `public`、`private``internal`。</span><span class="sxs-lookup"><span data-stu-id="b0374-128">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="b0374-129">有关详细信息，请参阅[访问控制](access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="b0374-129">For more information, see [Access Control](access-control.md).</span></span> <span data-ttu-id="b0374-130">默认值为 public。</span><span class="sxs-lookup"><span data-stu-id="b0374-130">The default is public.</span></span>

## <a name="referencing-code-in-modules"></a><span data-ttu-id="b0374-131">引用模块中的代码</span><span class="sxs-lookup"><span data-stu-id="b0374-131">Referencing Code in Modules</span></span>

<span data-ttu-id="b0374-132">当您从其他模块引用函数、类型和值时，您必须使用限定的名称或打开该模块。</span><span class="sxs-lookup"><span data-stu-id="b0374-132">When you reference functions, types, and values from another module, you must either use a qualified name or open the module.</span></span> <span data-ttu-id="b0374-133">如果使用限定名，则必须为所需的程序元素指定命名空间、模块和标识符。</span><span class="sxs-lookup"><span data-stu-id="b0374-133">If you use a qualified name, you must specify the namespaces, the module, and the identifier for the program element you want.</span></span> <span data-ttu-id="b0374-134">使用句点（.）分隔限定路径的每个部分，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b0374-134">You separate each part of the qualified path with a dot (.), as follows.</span></span>

`Namespace1.Namespace2.ModuleName.Identifier`

<span data-ttu-id="b0374-135">您可以打开该模块或一个或多个命名空间来简化代码。</span><span class="sxs-lookup"><span data-stu-id="b0374-135">You can open the module or one or more of the namespaces to simplify the code.</span></span> <span data-ttu-id="b0374-136">有关打开命名空间和模块的详细信息，请参阅[导入声明： `open` 关键字](import-declarations-the-open-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="b0374-136">For more information about opening namespaces and modules, see [Import Declarations: The `open` Keyword](import-declarations-the-open-keyword.md).</span></span>

<span data-ttu-id="b0374-137">下面的代码示例演示一个顶级模块，其中包含直到文件结尾的所有代码。</span><span class="sxs-lookup"><span data-stu-id="b0374-137">The following code example shows a top-level module that contains all the code up to the end of the file.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6604.fs)]

<span data-ttu-id="b0374-138">若要在同一项目中的另一个文件中使用此代码，请使用限定的名称，或者在使用函数之前打开该模块，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="b0374-138">To use this code from another file in the same project, you either use qualified names or you open the module before you use the functions, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a><span data-ttu-id="b0374-139">嵌套模块</span><span class="sxs-lookup"><span data-stu-id="b0374-139">Nested Modules</span></span>

<span data-ttu-id="b0374-140">模块可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="b0374-140">Modules can be nested.</span></span> <span data-ttu-id="b0374-141">内部模块必须缩进到外部模块声明，以指示它们是内部模块，而不是新模块。</span><span class="sxs-lookup"><span data-stu-id="b0374-141">Inner modules must be indented as far as outer module declarations to indicate that they are inner modules, not new modules.</span></span> <span data-ttu-id="b0374-142">例如，比较以下两个示例。</span><span class="sxs-lookup"><span data-stu-id="b0374-142">For example, compare the following two examples.</span></span> <span data-ttu-id="b0374-143">模块 `Z` 是以下代码中的内部模块。</span><span class="sxs-lookup"><span data-stu-id="b0374-143">Module `Z` is an inner module in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6607.fs)]

<span data-ttu-id="b0374-144">但模块 `Z` 是以下代码中模块 `Y` 的同级。</span><span class="sxs-lookup"><span data-stu-id="b0374-144">But module `Z` is a sibling to module `Y` in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6608.fs)]
<span data-ttu-id="b0374-145">模块 `Z` 在下面的代码中也是同级模块，因为它不会像模块 `Y`中的其他声明那样缩进。</span><span class="sxs-lookup"><span data-stu-id="b0374-145">Module `Z` is also a sibling module in the following code, because it is not indented as far as other declarations in module `Y`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6609.fs)]
<span data-ttu-id="b0374-146">最后，如果外部模块没有声明并且后跟另一个模块声明，则假定新的模块声明为内部模块，但编译器将在第二个模块定义的缩进距离小于1.</span><span class="sxs-lookup"><span data-stu-id="b0374-146">Finally, if the outer module has no declarations and is followed immediately by another module declaration, the new module declaration is assumed to be an inner module, but the compiler will warn you if the second module definition is not indented farther than the first.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6610.fs)]
<span data-ttu-id="b0374-147">若要消除此警告，请缩进内部模块。</span><span class="sxs-lookup"><span data-stu-id="b0374-147">To eliminate the warning, indent the inner module.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6611.fs)]
<span data-ttu-id="b0374-148">如果要将文件中的所有代码都放在单个外部模块中，并且需要内部模块，则外部模块不需要等号，而包含任何内部模块声明的声明（包括任何内部模块声明）无需缩进。</span><span class="sxs-lookup"><span data-stu-id="b0374-148">If you want all the code in a file to be in a single outer module and you want inner modules, the outer module does not require the equal sign, and the declarations, including any inner module declarations, that will go in the outer module do not have to be indented.</span></span> <span data-ttu-id="b0374-149">内部模块声明内的声明必须缩进。</span><span class="sxs-lookup"><span data-stu-id="b0374-149">Declarations inside the inner module declarations do have to be indented.</span></span> <span data-ttu-id="b0374-150">下面的代码演示了这种情况。</span><span class="sxs-lookup"><span data-stu-id="b0374-150">The following code shows this case.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a><span data-ttu-id="b0374-151">递归模块</span><span class="sxs-lookup"><span data-stu-id="b0374-151">Recursive modules</span></span>

<span data-ttu-id="b0374-152">F#4.1 引入了模块的概念，允许所有包含的代码相互递归。</span><span class="sxs-lookup"><span data-stu-id="b0374-152">F# 4.1 introduces the notion of modules which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="b0374-153">这是通过 `module rec`来完成的。</span><span class="sxs-lookup"><span data-stu-id="b0374-153">This is done via `module rec`.</span></span>  <span data-ttu-id="b0374-154">使用 `module rec` 可以减少无法在类型和模块之间编写相互引用代码的一些难题。</span><span class="sxs-lookup"><span data-stu-id="b0374-154">Use of `module rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="b0374-155">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="b0374-155">The following is an example of this:</span></span>

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

<span data-ttu-id="b0374-156">请注意，`DontSqueezeTheBananaException` 和类 `Banana` 的异常都相互引用。</span><span class="sxs-lookup"><span data-stu-id="b0374-156">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="b0374-157">此外，模块 `BananaHelpers` 和类 `Banana` 也相互引用。</span><span class="sxs-lookup"><span data-stu-id="b0374-157">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="b0374-158">如果从 `RecursiveModule` 模块中删除了 `rec` F#关键字，则无法在中进行表示。</span><span class="sxs-lookup"><span data-stu-id="b0374-158">This would not be possible to express in F# if you removed the `rec` keyword from the `RecursiveModule` module.</span></span>

<span data-ttu-id="b0374-159">此功能也可用于4.1 的F# [命名空间](namespaces.md)中。</span><span class="sxs-lookup"><span data-stu-id="b0374-159">This capability is also possible in [Namespaces](namespaces.md) with F# 4.1.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0374-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0374-160">See also</span></span>

- [<span data-ttu-id="b0374-161">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="b0374-161">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="b0374-162">命名空间</span><span class="sxs-lookup"><span data-stu-id="b0374-162">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="b0374-163">F#RFC FS-1009-允许在文件中的更大范围内进行相互引用类型和模块</span><span class="sxs-lookup"><span data-stu-id="b0374-163">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
