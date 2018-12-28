---
title: 导入声明：Open 关键字
description: 了解如何F#导入声明和如何指定模块或命名空间可以不使用完全限定的名称引用其中的元素。
ms.date: 05/16/2016
ms.openlocfilehash: 261ffdfdea2860db72b052b2ffeb5c7e5d652c24
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610315"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="d978d-103">导入声明：`open`关键字</span><span class="sxs-lookup"><span data-stu-id="d978d-103">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
> <span data-ttu-id="d978d-104">本文中的 API 参考链接将转至 MSDN。</span><span class="sxs-lookup"><span data-stu-id="d978d-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="d978d-105">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="d978d-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="d978d-106">*导入声明*指定模块或命名空间可以不使用完全限定的名称引用其中的元素。</span><span class="sxs-lookup"><span data-stu-id="d978d-106">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="d978d-107">语法</span><span class="sxs-lookup"><span data-stu-id="d978d-107">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="d978d-108">备注</span><span class="sxs-lookup"><span data-stu-id="d978d-108">Remarks</span></span>

<span data-ttu-id="d978d-109">使用完全限定的命名空间或模块路径来引用代码每次都可以创建很难编写、 读取和维护的代码。</span><span class="sxs-lookup"><span data-stu-id="d978d-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="d978d-110">相反，可以使用`open`关键字常用模块和命名空间，以便在引用该模块或命名空间的成员时，您可以使用名称的缩写形式而不是完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="d978d-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="d978d-111">此关键字是类似于`using`关键字在 C# 中， `using namespace` Visual c + +，和`Imports`在 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="d978d-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="d978d-112">模块或命名空间提供必须在同一项目中或在引用的项目或程序集中。</span><span class="sxs-lookup"><span data-stu-id="d978d-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="d978d-113">如果不是这样，可以添加到项目中，引用或使用`-reference`命令`-`行选项 (或其缩写， `-r`)。</span><span class="sxs-lookup"><span data-stu-id="d978d-113">If it is not, you can add a reference to the project, or use the `-reference` command`-`line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="d978d-114">有关详细信息，请参阅[编译器选项](compiler-options.md)。</span><span class="sxs-lookup"><span data-stu-id="d978d-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="d978d-115">导入声明使这些名称可以在下面的声明，直至封闭命名空间、 模块或文件的末尾的代码。</span><span class="sxs-lookup"><span data-stu-id="d978d-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="d978d-116">当使用多个导入声明时，它们应显示在单独的行上。</span><span class="sxs-lookup"><span data-stu-id="d978d-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="d978d-117">下面的代码演示如何使用`open`关键字来简化代码。</span><span class="sxs-lookup"><span data-stu-id="d978d-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="d978d-118">F#多个打开的模块或命名空间中出现相同的名称时，会出现多义性时，编译器不会发出错误或警告。</span><span class="sxs-lookup"><span data-stu-id="d978d-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="d978d-119">当出现多义性问题时，F#提供了对更多最近打开的模块或命名空间的首选项。</span><span class="sxs-lookup"><span data-stu-id="d978d-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="d978d-120">例如，在下面的代码中，`empty`意味着`Seq.empty`，即使`empty`位于在这种`List`和`Seq`模块。</span><span class="sxs-lookup"><span data-stu-id="d978d-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="d978d-121">因此，要小心，如打开模块或命名空间时`List`或`Seq`包含具有相同的名称; 相反，可考虑使用限定的名称的成员。</span><span class="sxs-lookup"><span data-stu-id="d978d-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="d978d-122">应避免任何情况下，在其中的代码是依赖于导入声明的顺序。</span><span class="sxs-lookup"><span data-stu-id="d978d-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="d978d-123">默认情况下打开的命名空间</span><span class="sxs-lookup"><span data-stu-id="d978d-123">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="d978d-124">一些命名空间相当频繁，因此可在F#而无需显式导入声明它们也隐式打开的代码。</span><span class="sxs-lookup"><span data-stu-id="d978d-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="d978d-125">下表显示了默认情况下打开的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d978d-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="d978d-126">命名空间</span><span class="sxs-lookup"><span data-stu-id="d978d-126">Namespace</span></span>|<span data-ttu-id="d978d-127">描述</span><span class="sxs-lookup"><span data-stu-id="d978d-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="d978d-128">包含基本F#类型的内置类型定义，如`int`并`float`。</span><span class="sxs-lookup"><span data-stu-id="d978d-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="d978d-129">包含基本算术运算，如`+`和`*`。</span><span class="sxs-lookup"><span data-stu-id="d978d-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="d978d-130">包含不可变集合类，例如`List`和`Array`。</span><span class="sxs-lookup"><span data-stu-id="d978d-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="d978d-131">包含用于控制构造，如惰性计算和异步工作流类型。</span><span class="sxs-lookup"><span data-stu-id="d978d-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="d978d-132">包含函数格式化 io，如`printf`函数。</span><span class="sxs-lookup"><span data-stu-id="d978d-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="d978d-133">AutoOpen 特性</span><span class="sxs-lookup"><span data-stu-id="d978d-133">AutoOpen Attribute</span></span>

<span data-ttu-id="d978d-134">您可以将应用`AutoOpen`属性对程序集，如果你想要引用的程序集时自动打开命名空间或模块。</span><span class="sxs-lookup"><span data-stu-id="d978d-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="d978d-135">您还可以应用`AutoOpen`要打开的父模块或命名空间时自动打开该模块的模块的属性。</span><span class="sxs-lookup"><span data-stu-id="d978d-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="d978d-136">有关详细信息，请参阅[Core.AutoOpenAttribute 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="d978d-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="d978d-137">RequireQualifiedAccess 特性</span><span class="sxs-lookup"><span data-stu-id="d978d-137">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="d978d-138">某些模块、 记录或联合类型可指定`RequireQualifiedAccess`属性。</span><span class="sxs-lookup"><span data-stu-id="d978d-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="d978d-139">在引用这些模块、 记录或联合中的元素时，必须使用而不考虑是否包括导入声明的限定的名称。</span><span class="sxs-lookup"><span data-stu-id="d978d-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="d978d-140">如果使用此属性有策略地进行上通常定义的类型使用的名称，帮助避免发生名称冲突，从而使代码更具弹性库中的更改。</span><span class="sxs-lookup"><span data-stu-id="d978d-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="d978d-141">有关详细信息，请参阅[Core.RequireQualifiedAccessAttribute 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D)。</span><span class="sxs-lookup"><span data-stu-id="d978d-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>

## <a name="see-also"></a><span data-ttu-id="d978d-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="d978d-142">See also</span></span>

- [<span data-ttu-id="d978d-143"># 语言参考</span><span class="sxs-lookup"><span data-stu-id="d978d-143"># Language Reference</span></span>](index.md)
- [<span data-ttu-id="d978d-144">命名空间</span><span class="sxs-lookup"><span data-stu-id="d978d-144">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="d978d-145">模块</span><span class="sxs-lookup"><span data-stu-id="d978d-145">Modules</span></span>](modules.md)