---
title: "导入声明：open 关键字 (F#)"
description: "了解有关 F # 导入声明和如何指定模块或命名空间可以无需使用完全限定的名称引用其元素。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1e98e48c-52e9-4314-8954-85d5583125f0
ms.openlocfilehash: a6d79bed3dd202657d06956edf9499a9b21a5f03
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="067c4-104">导入声明：`open`关键字</span><span class="sxs-lookup"><span data-stu-id="067c4-104">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
<span data-ttu-id="067c4-105">本文中的 API 参考链接将转至 MSDN。</span><span class="sxs-lookup"><span data-stu-id="067c4-105">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="067c4-106">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="067c4-106">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="067c4-107">*导入声明*指定模块或命名空间可以无需使用完全限定的名称引用其元素。</span><span class="sxs-lookup"><span data-stu-id="067c4-107">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>


## <a name="syntax"></a><span data-ttu-id="067c4-108">语法</span><span class="sxs-lookup"><span data-stu-id="067c4-108">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="067c4-109">备注</span><span class="sxs-lookup"><span data-stu-id="067c4-109">Remarks</span></span>
<span data-ttu-id="067c4-110">通过使用完全限定的命名空间或模块路径中引用代码每次可以创建很难写入、 读取和维护的代码。</span><span class="sxs-lookup"><span data-stu-id="067c4-110">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="067c4-111">相反，你可以使用`open`关键字经常使用的模块和命名空间，以便在引用该模块或命名空间的成员时，你可以使用名称的缩写形式，而不是完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="067c4-111">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="067c4-112">此关键字是类似于`using`关键字在 C# 中， `using namespace` Visual c + + 中和`Imports`在 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="067c4-112">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="067c4-113">模块或提供的命名空间必须是同一项目中或在引用的项目或程序集。</span><span class="sxs-lookup"><span data-stu-id="067c4-113">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="067c4-114">如果不是这样，你可以添加到项目中，引用或使用`-reference`命令`-`行选项 (或其缩写， `-r`)。</span><span class="sxs-lookup"><span data-stu-id="067c4-114">If it is not, you can add a reference to the project, or use the `-reference` command`-`line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="067c4-115">有关详细信息，请参阅[编译器选项](compiler-options.md)。</span><span class="sxs-lookup"><span data-stu-id="067c4-115">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="067c4-116">导入声明使这些名称在后面的声明，直至封闭命名空间、 模块或文件的末尾的代码中可用。</span><span class="sxs-lookup"><span data-stu-id="067c4-116">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="067c4-117">当使用多个导入声明时，它们应显示在单独的行。</span><span class="sxs-lookup"><span data-stu-id="067c4-117">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="067c4-118">下面的代码演示如何使用`open`关键字来简化代码。</span><span class="sxs-lookup"><span data-stu-id="067c4-118">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="067c4-119">F # 编译器不发出错误或警告，当多义性出现时多个打开的模块或命名空间中出现相同的名称。</span><span class="sxs-lookup"><span data-stu-id="067c4-119">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="067c4-120">出现多义性时，F # 提供首选项设置为更最近打开的模块或命名空间。</span><span class="sxs-lookup"><span data-stu-id="067c4-120">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="067c4-121">例如，在下面的代码中，`empty`意味着`Seq.empty`，即使`empty`位于同时`List`和`Seq`模块。</span><span class="sxs-lookup"><span data-stu-id="067c4-121">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="067c4-122">因此，请注意当你打开模块或命名空间如`List`或`Seq`了包含具有相同的名称; 相反，请考虑使用限定的名称的成员。</span><span class="sxs-lookup"><span data-stu-id="067c4-122">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="067c4-123">应避免任何情况下，在其中的代码是依赖于导入声明的顺序。</span><span class="sxs-lookup"><span data-stu-id="067c4-123">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>


## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="067c4-124">默认情况下打开的命名空间</span><span class="sxs-lookup"><span data-stu-id="067c4-124">Namespaces That Are Open by Default</span></span>
<span data-ttu-id="067c4-125">一些命名空间相当频繁，因此无需显式导入声明它们也隐式打开的 F # 代码中使用。</span><span class="sxs-lookup"><span data-stu-id="067c4-125">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="067c4-126">下表显示默认情况下打开的命名空间。</span><span class="sxs-lookup"><span data-stu-id="067c4-126">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="067c4-127">命名空间</span><span class="sxs-lookup"><span data-stu-id="067c4-127">Namespace</span></span>|<span data-ttu-id="067c4-128">描述</span><span class="sxs-lookup"><span data-stu-id="067c4-128">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="067c4-129">包含基本 F # 类型的内置类型定义，例如`int`和`float`。</span><span class="sxs-lookup"><span data-stu-id="067c4-129">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="067c4-130">包含基本算术运算，例如`+`和`*`。</span><span class="sxs-lookup"><span data-stu-id="067c4-130">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="067c4-131">包含不可变集合类，例如`List`和`Array`。</span><span class="sxs-lookup"><span data-stu-id="067c4-131">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="067c4-132">包含用于控制构造，如迟缓计算和异步工作流类型。</span><span class="sxs-lookup"><span data-stu-id="067c4-132">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="067c4-133">包含函数的格式化 IO，如`printf`函数。</span><span class="sxs-lookup"><span data-stu-id="067c4-133">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="067c4-134">AutoOpen 特性</span><span class="sxs-lookup"><span data-stu-id="067c4-134">AutoOpen Attribute</span></span>
<span data-ttu-id="067c4-135">你可以将应用`AutoOpen`特性的程序集，如果你想要引用的程序集时自动打开命名空间或模块。</span><span class="sxs-lookup"><span data-stu-id="067c4-135">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="067c4-136">你还可以应用`AutoOpen`属性设为要打开的父模块或命名空间时自动打开该模块的模块。</span><span class="sxs-lookup"><span data-stu-id="067c4-136">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="067c4-137">有关详细信息，请参阅[Core.AutoOpenAttribute 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="067c4-137">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>


## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="067c4-138">RequireQualifiedAccess 特性</span><span class="sxs-lookup"><span data-stu-id="067c4-138">RequireQualifiedAccess Attribute</span></span>
<span data-ttu-id="067c4-139">可以指定某些模块、 记录或联合类型`RequireQualifiedAccess`属性。</span><span class="sxs-lookup"><span data-stu-id="067c4-139">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="067c4-140">在引用这些模块、 记录或联合中的元素时，你必须使用无论是否包括导入声明限定的名称。</span><span class="sxs-lookup"><span data-stu-id="067c4-140">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="067c4-141">如果你上使用此特性有策略地进行定义常用的类型使用的名称，帮助避免名称冲突，从而使代码更具弹性到库中的更改。</span><span class="sxs-lookup"><span data-stu-id="067c4-141">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="067c4-142">有关详细信息，请参阅[Core.RequireQualifiedAccessAttribute 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D)。</span><span class="sxs-lookup"><span data-stu-id="067c4-142">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>


## <a name="see-also"></a><span data-ttu-id="067c4-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="067c4-143">See Also</span></span>
[<span data-ttu-id="067c4-144"># 语言参考</span><span class="sxs-lookup"><span data-stu-id="067c4-144"># Language Reference</span></span>](index.md)

[<span data-ttu-id="067c4-145">命名空间</span><span class="sxs-lookup"><span data-stu-id="067c4-145">Namespaces</span></span>](namespaces.md)

[<span data-ttu-id="067c4-146">模块</span><span class="sxs-lookup"><span data-stu-id="067c4-146">Modules</span></span>](modules.md)

