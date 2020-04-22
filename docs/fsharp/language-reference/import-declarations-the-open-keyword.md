---
title: 导入声明：open 关键字
description: 了解 F# 导入声明及其如何指定模块或命名空间，这些模块或命名空间的元素无需使用完全限定的名称即可引用。
ms.date: 04/04/2019
ms.openlocfilehash: 0baef27c7dc3181b9da0defb1c793fec04269c09
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021540"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="7c510-103">导入声明：`open` 关键字</span><span class="sxs-lookup"><span data-stu-id="7c510-103">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
> <span data-ttu-id="7c510-104">本文中的 API 参考链接将转至 MSDN。</span><span class="sxs-lookup"><span data-stu-id="7c510-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="7c510-105">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="7c510-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="7c510-106">*导入声明*指定一个模块或命名空间，这些模块或命名空间的元素无需使用完全限定的名称即可引用。</span><span class="sxs-lookup"><span data-stu-id="7c510-106">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="7c510-107">语法</span><span class="sxs-lookup"><span data-stu-id="7c510-107">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="7c510-108">备注</span><span class="sxs-lookup"><span data-stu-id="7c510-108">Remarks</span></span>

<span data-ttu-id="7c510-109">每次使用完全限定的命名空间或模块路径引用代码可以创建难以编写、读取和维护的代码。</span><span class="sxs-lookup"><span data-stu-id="7c510-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="7c510-110">相反，`open`您可以将 关键字用于常用的模块和命名空间，以便在引用该模块或命名空间的成员时，可以使用名称的简短形式而不是完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="7c510-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="7c510-111">此关键字类似于 C#`using`中的关键字、Visual `using namespace` C++ 和`Imports`Visual Basic 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="7c510-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="7c510-112">提供的模块或命名空间必须位于同一项目或引用的项目或程序集中。</span><span class="sxs-lookup"><span data-stu-id="7c510-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="7c510-113">如果不是，则可以添加对项目的引用，或使用`-reference`命令行选项（或其缩写。 `-r`</span><span class="sxs-lookup"><span data-stu-id="7c510-113">If it is not, you can add a reference to the project, or use the `-reference` command-line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="7c510-114">有关详细信息，请参阅[编译器选项](compiler-options.md)。</span><span class="sxs-lookup"><span data-stu-id="7c510-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="7c510-115">导入声明使声明后面的代码中的名称可用，最多到封闭命名空间、模块或文件的结尾。</span><span class="sxs-lookup"><span data-stu-id="7c510-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="7c510-116">使用多个导入声明时，它们应显示在单独的行上。</span><span class="sxs-lookup"><span data-stu-id="7c510-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="7c510-117">以下代码显示了`open`关键字用于简化代码的使用。</span><span class="sxs-lookup"><span data-stu-id="7c510-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="7c510-118">当多个打开的模块或命名空间中出现相同名称时，F# 编译器不会发出错误或警告。</span><span class="sxs-lookup"><span data-stu-id="7c510-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="7c510-119">当出现模棱两可时，F# 优先考虑最近打开的模块或命名空间。</span><span class="sxs-lookup"><span data-stu-id="7c510-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="7c510-120">例如，在以下代码中，`empty`表示`Seq.empty`，即使`empty`位于 和`List``Seq`模块中也是如此。</span><span class="sxs-lookup"><span data-stu-id="7c510-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="7c510-121">因此，在打开模块或命名空间（如`List`或`Seq`包含具有相同名称的成员）时要小心;相反，请考虑使用限定名称。</span><span class="sxs-lookup"><span data-stu-id="7c510-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="7c510-122">应避免代码依赖于导入声明的顺序的任何情况。</span><span class="sxs-lookup"><span data-stu-id="7c510-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="7c510-123">默认情况下打开的命名空间</span><span class="sxs-lookup"><span data-stu-id="7c510-123">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="7c510-124">某些命名空间在 F# 代码中非常频繁，因此无需显式导入声明即可隐式打开。</span><span class="sxs-lookup"><span data-stu-id="7c510-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="7c510-125">下表显示了默认情况下打开的命名空间。</span><span class="sxs-lookup"><span data-stu-id="7c510-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="7c510-126">命名空间</span><span class="sxs-lookup"><span data-stu-id="7c510-126">Namespace</span></span>|<span data-ttu-id="7c510-127">说明</span><span class="sxs-lookup"><span data-stu-id="7c510-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="7c510-128">包含内置类型（如 和`int``float`） 的基本 F# 类型定义。</span><span class="sxs-lookup"><span data-stu-id="7c510-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="7c510-129">包含基本算术运算，如`+``*`和 。</span><span class="sxs-lookup"><span data-stu-id="7c510-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="7c510-130">包含不可变的集合类，`List`如 和`Array`。</span><span class="sxs-lookup"><span data-stu-id="7c510-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="7c510-131">包含控件构造的类型，如惰性评估和异步工作流。</span><span class="sxs-lookup"><span data-stu-id="7c510-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="7c510-132">包含格式化 IO 的功能，`printf`如函数。</span><span class="sxs-lookup"><span data-stu-id="7c510-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="7c510-133">自动打开属性</span><span class="sxs-lookup"><span data-stu-id="7c510-133">AutoOpen Attribute</span></span>

<span data-ttu-id="7c510-134">如果要在引用程序集`AutoOpen`时自动打开命名空间或模块，则可以将该属性应用于程序集。</span><span class="sxs-lookup"><span data-stu-id="7c510-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="7c510-135">您还可以将`AutoOpen`该属性应用于模块，以在打开父模块或命名空间时自动打开该模块。</span><span class="sxs-lookup"><span data-stu-id="7c510-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="7c510-136">有关详细信息，请参阅[Core.AutoOpenattribute 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="7c510-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="7c510-137">需要限定访问属性</span><span class="sxs-lookup"><span data-stu-id="7c510-137">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="7c510-138">某些模块、记录或联合类型可以指定该`RequireQualifiedAccess`属性。</span><span class="sxs-lookup"><span data-stu-id="7c510-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="7c510-139">引用这些模块、记录或联合的元素时，无论是否包含导入声明，都必须使用限定名称。</span><span class="sxs-lookup"><span data-stu-id="7c510-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="7c510-140">如果在定义常用名称的类型上战略性地使用此属性，则有助于避免名称冲突，从而使代码对库中的更改更具弹性。</span><span class="sxs-lookup"><span data-stu-id="7c510-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="7c510-141">有关详细信息，请参阅[Core.要求限定Access属性类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D)。</span><span class="sxs-lookup"><span data-stu-id="7c510-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>

## <a name="see-also"></a><span data-ttu-id="7c510-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c510-142">See also</span></span>

- [<span data-ttu-id="7c510-143">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="7c510-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="7c510-144">命名空间</span><span class="sxs-lookup"><span data-stu-id="7c510-144">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="7c510-145">模块</span><span class="sxs-lookup"><span data-stu-id="7c510-145">Modules</span></span>](modules.md)
