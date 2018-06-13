---
title: 'F # 组件设计准则'
description: '了解有关编写 F # 组件消耗旨在由其他调用方的准则。'
ms.date: 05/14/2018
ms.openlocfilehash: 7e71710b1bc2fe3e8d7a5a091513a1432650dc04
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2018
ms.locfileid: "34458081"
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="0f56e-103">F # 组件设计准则</span><span class="sxs-lookup"><span data-stu-id="0f56e-103">F# component design guidelines</span></span>

<span data-ttu-id="0f56e-104">本文档是一组的 F # 编程，F # 组件设计准则，v14，Microsoft Research 所基于的组件设计指导原则和[另一个版本](https://fsharp.org/specs/component-design-guidelines/)最初策展和 F # Software Foundation 由维护。</span><span class="sxs-lookup"><span data-stu-id="0f56e-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and [another version](https://fsharp.org/specs/component-design-guidelines/) originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="0f56e-105">本文档假定你熟悉 F # 编程。</span><span class="sxs-lookup"><span data-stu-id="0f56e-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="0f56e-106">非常感谢 F # 社区的贡献和在本指南的各个版本很有帮助的反馈。</span><span class="sxs-lookup"><span data-stu-id="0f56e-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="0f56e-107">概述</span><span class="sxs-lookup"><span data-stu-id="0f56e-107">Overview</span></span>

<span data-ttu-id="0f56e-108">本文档考察某些 F # 组件设计和编码与相关的问题。</span><span class="sxs-lookup"><span data-stu-id="0f56e-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="0f56e-109">组件可能意味着以下任一项：</span><span class="sxs-lookup"><span data-stu-id="0f56e-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="0f56e-110">你已在该项目中的外部使用者的 F # 项目中的图层。</span><span class="sxs-lookup"><span data-stu-id="0f56e-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="0f56e-111">跨程序集边界中适合由 F # 代码使用库。</span><span class="sxs-lookup"><span data-stu-id="0f56e-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="0f56e-112">跨程序集边界中适合由任何.NET 语言消耗库。</span><span class="sxs-lookup"><span data-stu-id="0f56e-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="0f56e-113">如适用于分发的包存储库中，通过库[NuGet](https://nuget.org)。</span><span class="sxs-lookup"><span data-stu-id="0f56e-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="0f56e-114">请按照本文中所述的技术[的良好的 F # 代码的五个原则](index.md#five-principles-of-good-f-code)，从而利用同时功能和对象根据编程。</span><span class="sxs-lookup"><span data-stu-id="0f56e-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="0f56e-115">方法，无论组件和库设计器将尝试创建一个 API，可轻松由开发人员时面临实际和实际问题很的多。</span><span class="sxs-lookup"><span data-stu-id="0f56e-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="0f56e-116">负责任的应用程序的[.NET 库设计准则](../../standard/design-guidelines/index.md)将引导你创建一组一致的愉快若要使用的 Api。</span><span class="sxs-lookup"><span data-stu-id="0f56e-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="0f56e-117">通用准则</span><span class="sxs-lookup"><span data-stu-id="0f56e-117">General guidelines</span></span>

<span data-ttu-id="0f56e-118">有几个通用准则适用于 F # 库，而不考虑库的目标受众。</span><span class="sxs-lookup"><span data-stu-id="0f56e-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="0f56e-119">了解.NET 库设计准则</span><span class="sxs-lookup"><span data-stu-id="0f56e-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="0f56e-120">F # 编码你正在的种类，无论它是有价值的工作掌握[.NET 库设计准则](../../standard/design-guidelines/index.md)。</span><span class="sxs-lookup"><span data-stu-id="0f56e-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="0f56e-121">大多数其他 F #.NET 程序员熟悉这些准则，并预期.NET 代码以符合它们。</span><span class="sxs-lookup"><span data-stu-id="0f56e-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="0f56e-122">.NET 类库设计指南提供有关命名、 设计类和接口、 成员 （属性、 方法、 事件等） 的设计和的详细信息，常规指南，并且是有用的第一个点的各种不同的设计指南的引用。</span><span class="sxs-lookup"><span data-stu-id="0f56e-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="0f56e-123">将 XML 文档注释添加到你的代码</span><span class="sxs-lookup"><span data-stu-id="0f56e-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="0f56e-124">公共 Api 的 XML 文档确保用户可以获得很好的 Intellisense 和快速信息，使用这些类型和成员，以及启用生成文档文件库时。</span><span class="sxs-lookup"><span data-stu-id="0f56e-124">XML documentation on public APIs ensure that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="0f56e-125">请参阅[XML 文档](../language-reference/xml-documentation.md)有关可以用于 xmldoc 注释内的附加标记的各种 xml 标记。</span><span class="sxs-lookup"><span data-stu-id="0f56e-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

<span data-ttu-id="0f56e-126">你可以使用缩写形式 XML 注释 (`/// comment`)，或标准的 XML 注释 (`///<summary>comment</summary>`)。</span><span class="sxs-lookup"><span data-stu-id="0f56e-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="0f56e-127">请考虑稳定的库和组件 Api 使用显式的签名文件 (.fsi)</span><span class="sxs-lookup"><span data-stu-id="0f56e-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="0f56e-128">使用显式的签名文件的 F # 库中提供公共 API，这两者都可帮助确保，你知道的完整公共接口的你的库，以及提供完全分离之间公用文档和内部简洁的摘要实现详细信息。</span><span class="sxs-lookup"><span data-stu-id="0f56e-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which both helps to ensure that you know the full public surface of your library, as well as provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="0f56e-129">请注意，签名文件将摩擦添加到更改公共 API，通过要求在实现和签名文件中进行更改。</span><span class="sxs-lookup"><span data-stu-id="0f56e-129">Note that signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="0f56e-130">因此，签名文件应通常仅引入时 API 具有成为巩固并且不再需要重大更改。</span><span class="sxs-lookup"><span data-stu-id="0f56e-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="0f56e-131">始终遵循在.NET 中使用字符串的最佳实践</span><span class="sxs-lookup"><span data-stu-id="0f56e-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="0f56e-132">请按照[在.NET 中使用字符串的最佳实践](../../standard/base-types/best-practices-strings.md)指南。</span><span class="sxs-lookup"><span data-stu-id="0f56e-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="0f56e-133">具体而言，始终显式声明*区域性意向*中的转换和比较字符串 （如果适用）。</span><span class="sxs-lookup"><span data-stu-id="0f56e-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="0f56e-134">F # 的准则-面向库</span><span class="sxs-lookup"><span data-stu-id="0f56e-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="0f56e-135">本节提供有关在开发公共 F # 的建议-面向库;也就是说，公开公共 Api 旨在由 F # 开发人员使用的库。</span><span class="sxs-lookup"><span data-stu-id="0f56e-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="0f56e-136">没有特定于 F # 适用的各种库设计建议。</span><span class="sxs-lookup"><span data-stu-id="0f56e-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="0f56e-137">如果未指定特定后面的建议，在.NET 库设计准则是回退的指南。</span><span class="sxs-lookup"><span data-stu-id="0f56e-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="0f56e-138">命名约定</span><span class="sxs-lookup"><span data-stu-id="0f56e-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="0f56e-139">使用.NET 命名和大小写约定</span><span class="sxs-lookup"><span data-stu-id="0f56e-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="0f56e-140">下表遵循.NET 命名和大小写约定。</span><span class="sxs-lookup"><span data-stu-id="0f56e-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="0f56e-141">有小添加项。 还包括 F # 构造。</span><span class="sxs-lookup"><span data-stu-id="0f56e-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="0f56e-142">构造</span><span class="sxs-lookup"><span data-stu-id="0f56e-142">Construct</span></span> | <span data-ttu-id="0f56e-143">Case</span><span class="sxs-lookup"><span data-stu-id="0f56e-143">Case</span></span> | <span data-ttu-id="0f56e-144">部件</span><span class="sxs-lookup"><span data-stu-id="0f56e-144">Part</span></span> | <span data-ttu-id="0f56e-145">示例</span><span class="sxs-lookup"><span data-stu-id="0f56e-145">Examples</span></span> | <span data-ttu-id="0f56e-146">说明</span><span class="sxs-lookup"><span data-stu-id="0f56e-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="0f56e-147">具体类型</span><span class="sxs-lookup"><span data-stu-id="0f56e-147">Concrete types</span></span> | <span data-ttu-id="0f56e-148">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0f56e-148">PascalCase</span></span> | <span data-ttu-id="0f56e-149">名词 / 形容词</span><span class="sxs-lookup"><span data-stu-id="0f56e-149">Noun/ adjective</span></span> | <span data-ttu-id="0f56e-150">列表中，双精度，复杂</span><span class="sxs-lookup"><span data-stu-id="0f56e-150">List, Double, Complex</span></span> | <span data-ttu-id="0f56e-151">具体类型是结构、 类、 枚举、 委托、 记录和联合。</span><span class="sxs-lookup"><span data-stu-id="0f56e-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="0f56e-152">尽管类型名称是在 OCaml 传统上小写，F # 已采用了.NET 类型的命名方案。</span><span class="sxs-lookup"><span data-stu-id="0f56e-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="0f56e-153">DLL</span><span class="sxs-lookup"><span data-stu-id="0f56e-153">DLLs</span></span>           | <span data-ttu-id="0f56e-154">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0f56e-154">PascalCase</span></span> |                 | <span data-ttu-id="0f56e-155">Fabrikam.Core.dll</span><span class="sxs-lookup"><span data-stu-id="0f56e-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="0f56e-156">联合标记</span><span class="sxs-lookup"><span data-stu-id="0f56e-156">Union tags</span></span>     | <span data-ttu-id="0f56e-157">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0f56e-157">PascalCase</span></span> | <span data-ttu-id="0f56e-158">名词</span><span class="sxs-lookup"><span data-stu-id="0f56e-158">Noun</span></span> | <span data-ttu-id="0f56e-159">一些，添加成功</span><span class="sxs-lookup"><span data-stu-id="0f56e-159">Some, Add, Success</span></span> | <span data-ttu-id="0f56e-160">不要在公共 Api 中使用前缀。</span><span class="sxs-lookup"><span data-stu-id="0f56e-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="0f56e-161">（可选） 使用的前缀时内部，如键入团队 = TAlpha</span><span class="sxs-lookup"><span data-stu-id="0f56e-161">Optionally use a prefix when internal, such as \`\`\`type Teams = TAlpha</span></span> | <span data-ttu-id="0f56e-162">TBeta</span><span class="sxs-lookup"><span data-stu-id="0f56e-162">TBeta</span></span> | <span data-ttu-id="0f56e-163">TDelta。 ' '</span><span class="sxs-lookup"><span data-stu-id="0f56e-163">TDelta.\`\`\`</span></span> |
| <span data-ttu-id="0f56e-164">事件</span><span class="sxs-lookup"><span data-stu-id="0f56e-164">Event</span></span>          | <span data-ttu-id="0f56e-165">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0f56e-165">PascalCase</span></span> | <span data-ttu-id="0f56e-166">谓词</span><span class="sxs-lookup"><span data-stu-id="0f56e-166">Verb</span></span> | <span data-ttu-id="0f56e-167">ValueChanged / ValueChanging</span><span class="sxs-lookup"><span data-stu-id="0f56e-167">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="0f56e-168">异常</span><span class="sxs-lookup"><span data-stu-id="0f56e-168">Exceptions</span></span>     | <span data-ttu-id="0f56e-169">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0f56e-169">PascalCase</span></span> |      | <span data-ttu-id="0f56e-170">WebException</span><span class="sxs-lookup"><span data-stu-id="0f56e-170">WebException</span></span> | <span data-ttu-id="0f56e-171">名称应以"异常"结尾。</span><span class="sxs-lookup"><span data-stu-id="0f56e-171">Name should end with “Exception”.</span></span> |
| <span data-ttu-id="0f56e-172">字段</span><span class="sxs-lookup"><span data-stu-id="0f56e-172">Field</span></span>          | <span data-ttu-id="0f56e-173">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0f56e-173">PascalCase</span></span> | <span data-ttu-id="0f56e-174">名词</span><span class="sxs-lookup"><span data-stu-id="0f56e-174">Noun</span></span> | <span data-ttu-id="0f56e-175">CurrentName</span><span class="sxs-lookup"><span data-stu-id="0f56e-175">CurrentName</span></span>  | |
| <span data-ttu-id="0f56e-176">接口类型</span><span class="sxs-lookup"><span data-stu-id="0f56e-176">Interface types</span></span> |  <span data-ttu-id="0f56e-177">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0f56e-177">PascalCase</span></span> | <span data-ttu-id="0f56e-178">名词 / 形容词</span><span class="sxs-lookup"><span data-stu-id="0f56e-178">Noun/ adjective</span></span> | <span data-ttu-id="0f56e-179">IDisposable</span><span class="sxs-lookup"><span data-stu-id="0f56e-179">IDisposable</span></span> | <span data-ttu-id="0f56e-180">名称应以"I"开头。</span><span class="sxs-lookup"><span data-stu-id="0f56e-180">Name should start with “I”.</span></span> |
| <span data-ttu-id="0f56e-181">方法</span><span class="sxs-lookup"><span data-stu-id="0f56e-181">Method</span></span> |  <span data-ttu-id="0f56e-182">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0f56e-182">PascalCase</span></span> |  <span data-ttu-id="0f56e-183">谓词</span><span class="sxs-lookup"><span data-stu-id="0f56e-183">Verb</span></span> | <span data-ttu-id="0f56e-184">ToString</span><span class="sxs-lookup"><span data-stu-id="0f56e-184">ToString</span></span> | |
| <span data-ttu-id="0f56e-185">命名空间</span><span class="sxs-lookup"><span data-stu-id="0f56e-185">Namespace</span></span> | <span data-ttu-id="0f56e-186">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0f56e-186">PascalCase</span></span> | | <span data-ttu-id="0f56e-187">Microsoft.FSharp.Core</span><span class="sxs-lookup"><span data-stu-id="0f56e-187">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="0f56e-188">通常使用`<Organization>.<Technology>[.<Subnamespace>]`，但删除组织如果技术无关的组织。</span><span class="sxs-lookup"><span data-stu-id="0f56e-188">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="0f56e-189">参数</span><span class="sxs-lookup"><span data-stu-id="0f56e-189">Parameters</span></span> | <span data-ttu-id="0f56e-190">驼峰匹配</span><span class="sxs-lookup"><span data-stu-id="0f56e-190">camelCase</span></span> | <span data-ttu-id="0f56e-191">名词</span><span class="sxs-lookup"><span data-stu-id="0f56e-191">Noun</span></span> |  <span data-ttu-id="0f56e-192">类型名称、 转换、 范围</span><span class="sxs-lookup"><span data-stu-id="0f56e-192">typeName, transform, range</span></span> | |
| <span data-ttu-id="0f56e-193">允许值 （内部）</span><span class="sxs-lookup"><span data-stu-id="0f56e-193">let values (internal)</span></span> | <span data-ttu-id="0f56e-194">驼峰匹配或 PascalCase</span><span class="sxs-lookup"><span data-stu-id="0f56e-194">camelCase or PascalCase</span></span> | <span data-ttu-id="0f56e-195">名词 / 谓词</span><span class="sxs-lookup"><span data-stu-id="0f56e-195">Noun/ verb</span></span> |  <span data-ttu-id="0f56e-196">getValue myTable</span><span class="sxs-lookup"><span data-stu-id="0f56e-196">getValue, myTable</span></span> |
| <span data-ttu-id="0f56e-197">允许值 （外部）</span><span class="sxs-lookup"><span data-stu-id="0f56e-197">let values (external)</span></span> | <span data-ttu-id="0f56e-198">驼峰匹配或 PascalCase</span><span class="sxs-lookup"><span data-stu-id="0f56e-198">camelCase or PascalCase</span></span> | <span data-ttu-id="0f56e-199">名词/谓词</span><span class="sxs-lookup"><span data-stu-id="0f56e-199">Noun/verb</span></span>  | <span data-ttu-id="0f56e-200">List.map Dates.Today</span><span class="sxs-lookup"><span data-stu-id="0f56e-200">List.map, Dates.Today</span></span> | <span data-ttu-id="0f56e-201">let 绑定值通常是公共的遵循传统功能的设计模式时。</span><span class="sxs-lookup"><span data-stu-id="0f56e-201">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="0f56e-202">但是，通常使用出现可从其他.NET 语言中使用标识符的 PascalCase。</span><span class="sxs-lookup"><span data-stu-id="0f56e-202">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="0f56e-203">属性</span><span class="sxs-lookup"><span data-stu-id="0f56e-203">Property</span></span>  | <span data-ttu-id="0f56e-204">PascalCase</span><span class="sxs-lookup"><span data-stu-id="0f56e-204">PascalCase</span></span>  | <span data-ttu-id="0f56e-205">名词 / 形容词</span><span class="sxs-lookup"><span data-stu-id="0f56e-205">Noun/ adjective</span></span>  | <span data-ttu-id="0f56e-206">IsEndOfFile，背景色</span><span class="sxs-lookup"><span data-stu-id="0f56e-206">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="0f56e-207">布尔值属性通常使用并且可以并且应该赞成，如下所示 IsEndOfFile，不 IsNotEndOfFile。</span><span class="sxs-lookup"><span data-stu-id="0f56e-207">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="0f56e-208">避免缩写</span><span class="sxs-lookup"><span data-stu-id="0f56e-208">Avoid abbreviations</span></span>

<span data-ttu-id="0f56e-209">.NET 准则禁止使用缩写 (例如，"使用`OnButtonClick`而非`OnBtnClick`")。</span><span class="sxs-lookup"><span data-stu-id="0f56e-209">The .NET guidelines discourage the use of abbreviations (for example, “use `OnButtonClick` rather than `OnBtnClick`”).</span></span> <span data-ttu-id="0f56e-210">常见的缩写，如`Async`允许为"异步"。</span><span class="sxs-lookup"><span data-stu-id="0f56e-210">Common abbreviations, such as `Async` for “Asynchronous”, are tolerated.</span></span> <span data-ttu-id="0f56e-211">对于函数编程;，有时将忽略此原则例如，`List.iter`用于缩写"循环"。</span><span class="sxs-lookup"><span data-stu-id="0f56e-211">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for “iterate”.</span></span> <span data-ttu-id="0f56e-212">因此，使用缩写倾向于 F # 中在更大程度容忍-到-F # 编程，但仍通常应当避免在公共组件设计。</span><span class="sxs-lookup"><span data-stu-id="0f56e-212">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="0f56e-213">避免名称冲突的大小写</span><span class="sxs-lookup"><span data-stu-id="0f56e-213">Avoid casing name collisions</span></span>

<span data-ttu-id="0f56e-214">.NET 准则说，单独的大小写不能用于消除歧义名称冲突，因为某些客户端语言 (例如，Visual Basic 中) 不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0f56e-214">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="0f56e-215">在适用处使用首字母缩写词</span><span class="sxs-lookup"><span data-stu-id="0f56e-215">Use acronyms where appropriate</span></span>

<span data-ttu-id="0f56e-216">首字母缩写词，如 XML 不缩写，并在首字母未大写形式 (Xml) 的.NET 库中广泛使用。</span><span class="sxs-lookup"><span data-stu-id="0f56e-216">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="0f56e-217">仅应使用的已知的广泛认可首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="0f56e-217">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="0f56e-218">为泛型参数的名称使用 PascalCase</span><span class="sxs-lookup"><span data-stu-id="0f56e-218">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="0f56e-219">为用于公共 Api，包括 F # 中的泛型参数名称 PascalCase-面向库。</span><span class="sxs-lookup"><span data-stu-id="0f56e-219">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="0f56e-220">具体而言，使用类似名称`T`， `U`， `T1`，`T2`任意泛型参数，并且当特定的名称会使其意义上，然后对于 F #-面向库使用类似名称`Key`， `Value`， `Arg`(但不是例如`TKey`)。</span><span class="sxs-lookup"><span data-stu-id="0f56e-220">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="0f56e-221">对公共函数和 F # 模块中的值使用 PascalCase 或驼峰匹配</span><span class="sxs-lookup"><span data-stu-id="0f56e-221">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="0f56e-222">驼峰匹配用于为用于而设计的公共函数不合格 (例如， `invalidArg`)，和"标准集合函数"（例如 List.map）。</span><span class="sxs-lookup"><span data-stu-id="0f56e-222">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the “standard collection functions” (for example, List.map).</span></span> <span data-ttu-id="0f56e-223">在这两个这些情况下，函数名称作用类似语言中的关键字。</span><span class="sxs-lookup"><span data-stu-id="0f56e-223">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="0f56e-224">对象、 类型和模块的设计</span><span class="sxs-lookup"><span data-stu-id="0f56e-224">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="0f56e-225">使用命名空间或模块来包含类型和模块</span><span class="sxs-lookup"><span data-stu-id="0f56e-225">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="0f56e-226">组件中的每个 F # 文件应命名空间声明或模块声明开头。</span><span class="sxs-lookup"><span data-stu-id="0f56e-226">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="0f56e-227">或</span><span class="sxs-lookup"><span data-stu-id="0f56e-227">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="0f56e-228">使用模块和命名空间将代码最高级别组织之间的差异如下所示：</span><span class="sxs-lookup"><span data-stu-id="0f56e-228">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="0f56e-229">命名空间可以跨多个文件</span><span class="sxs-lookup"><span data-stu-id="0f56e-229">Namespaces can span multiple files</span></span>
* <span data-ttu-id="0f56e-230">命名空间不能包含 F # 函数，除非它们是在一个内部模块</span><span class="sxs-lookup"><span data-stu-id="0f56e-230">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="0f56e-231">任何给定模块的代码必须包含在单个文件</span><span class="sxs-lookup"><span data-stu-id="0f56e-231">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="0f56e-232">顶级模块可以包含无需内部模块的 F # 函数</span><span class="sxs-lookup"><span data-stu-id="0f56e-232">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="0f56e-233">顶级命名空间或模块之间的选择会影响的代码的已编译的形式，因此将影响将视图从其他.NET 语言应你的 API 最终使用 F # 代码外部。</span><span class="sxs-lookup"><span data-stu-id="0f56e-233">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="0f56e-234">用于操作固有的对象类型的方法和属性</span><span class="sxs-lookup"><span data-stu-id="0f56e-234">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="0f56e-235">当使用对象时，最好是以确保可使用的功能实现与方法和该类型上的属性。</span><span class="sxs-lookup"><span data-stu-id="0f56e-235">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="0f56e-236">给定成员的大容量的功能需要不一定在中实现该成员，但该功能的使用部分应。</span><span class="sxs-lookup"><span data-stu-id="0f56e-236">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="0f56e-237">使用类来封装可变状态</span><span class="sxs-lookup"><span data-stu-id="0f56e-237">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="0f56e-238">在 F # 中，这只需进行其中状态不已封装由另一种语言构造，如闭包、 序列表达式或异步计算。</span><span class="sxs-lookup"><span data-stu-id="0f56e-238">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="0f56e-239">接口用于组相关的操作</span><span class="sxs-lookup"><span data-stu-id="0f56e-239">Use interfaces to group related operations</span></span>

<span data-ttu-id="0f56e-240">使用接口类型来表示一组的操作。</span><span class="sxs-lookup"><span data-stu-id="0f56e-240">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="0f56e-241">这是优先于其他选项，如元组的函数或函数的记录。</span><span class="sxs-lookup"><span data-stu-id="0f56e-241">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="0f56e-242">优先于：</span><span class="sxs-lookup"><span data-stu-id="0f56e-242">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

<span data-ttu-id="0f56e-243">接口是在.NET 中，可以用于实现什么函子将通常为您提供的第一类概念。</span><span class="sxs-lookup"><span data-stu-id="0f56e-243">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="0f56e-244">此外，它们可以用于对现有类型到你的程序，记录的函数不能进行编码。</span><span class="sxs-lookup"><span data-stu-id="0f56e-244">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a><span data-ttu-id="0f56e-245">在集合上使用组功能的作用到模块</span><span class="sxs-lookup"><span data-stu-id="0f56e-245">Use a module to group functions which act on collections</span></span>

<span data-ttu-id="0f56e-246">在定义集合类型时，请考虑提供一组标准的操作如`CollectionType.map`和`CollectionType.iter`) 的新集合类型。</span><span class="sxs-lookup"><span data-stu-id="0f56e-246">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="0f56e-247">如果包含此类模块，请按照在 FSharp.Core 中找到的函数的标准命名约定。</span><span class="sxs-lookup"><span data-stu-id="0f56e-247">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="0f56e-248">对于通用、 规范函数，特别是在数学和 DSL 库使用的组函数的模块</span><span class="sxs-lookup"><span data-stu-id="0f56e-248">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="0f56e-249">例如，`Microsoft.FSharp.Core.Operators`为自动打开的集合的顶级函数 (如`abs`和`sin`) 由 FSharp.Core.dll。</span><span class="sxs-lookup"><span data-stu-id="0f56e-249">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="0f56e-250">同样，统计信息库可能包含函数的模块`erf`和`erfc`，而此模块用于显式或自动打开。</span><span class="sxs-lookup"><span data-stu-id="0f56e-250">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="0f56e-251">请考虑使用 RequireQualifiedAccess 并仔细应用 AutoOpen 特性</span><span class="sxs-lookup"><span data-stu-id="0f56e-251">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="0f56e-252">添加`[<RequireQualifiedAccess>]`模块的属性指示模块可能无法打开，并对该模块的元素的引用，需要显式限定访问权限。</span><span class="sxs-lookup"><span data-stu-id="0f56e-252">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="0f56e-253">例如，`Microsoft.FSharp.Collections.List`模块具有此属性。</span><span class="sxs-lookup"><span data-stu-id="0f56e-253">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="0f56e-254">时函数和模块中的值可能与其他模块中的名称发生冲突的名称，这会很有用。</span><span class="sxs-lookup"><span data-stu-id="0f56e-254">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="0f56e-255">需限定的访问会大大增加的长期的可维护性和 evolvability 的库。</span><span class="sxs-lookup"><span data-stu-id="0f56e-255">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="0f56e-256">添加`[<AutoOpen>]`模块特性意味着打开包含的命名空间时，将打开模块。</span><span class="sxs-lookup"><span data-stu-id="0f56e-256">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="0f56e-257">`[<AutoOpen>]`属性还可应用于程序集可指示引用的程序集时自动打开模块。</span><span class="sxs-lookup"><span data-stu-id="0f56e-257">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="0f56e-258">例如，统计信息库**MathsHeaven.Statistics**可能包含`module MathsHeaven.Statistics.Operators`包含函数`erf`和`erfc`。</span><span class="sxs-lookup"><span data-stu-id="0f56e-258">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="0f56e-259">可以将标记为此模块是合理的`[<AutoOpen>]`。</span><span class="sxs-lookup"><span data-stu-id="0f56e-259">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="0f56e-260">这意味着`open MathsHeaven.Statistics`也将打开此模块并将名称`erf`和`erfc`纳入范围。</span><span class="sxs-lookup"><span data-stu-id="0f56e-260">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="0f56e-261">使用另一个良好`[<AutoOpen>]`为包含扩展方法的模块。</span><span class="sxs-lookup"><span data-stu-id="0f56e-261">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="0f56e-262">因为过度使用的`[<AutoOpen>]`应谨慎使用导致生成受到污染命名空间和属性。</span><span class="sxs-lookup"><span data-stu-id="0f56e-262">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="0f56e-263">在特定域中，合理地使用的特定库`[<AutoOpen>]`可能会导致更好的可用性。</span><span class="sxs-lookup"><span data-stu-id="0f56e-263">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="0f56e-264">请考虑在其中使用的已知运算符是适当的类上定义运算符成员</span><span class="sxs-lookup"><span data-stu-id="0f56e-264">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="0f56e-265">有时使用类来建模数学构造，如向量。</span><span class="sxs-lookup"><span data-stu-id="0f56e-265">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="0f56e-266">当要建模的域具有已知的运算符时，作为成员固有的类定义它们非常有用。</span><span class="sxs-lookup"><span data-stu-id="0f56e-266">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="0f56e-267">本指南对应于为这些类型的常规.NET 指南。</span><span class="sxs-lookup"><span data-stu-id="0f56e-267">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="0f56e-268">但是，它可以是此外重要的 F # 编码因为这会使这些类型以在 F # 函数结合和成员的约束，如 List.sumBy 方法中使用。</span><span class="sxs-lookup"><span data-stu-id="0f56e-268">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="0f56e-269">请考虑使用 CompiledName 来提供。用于其他.NET 语言消耗者的网络的友好名称</span><span class="sxs-lookup"><span data-stu-id="0f56e-269">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="0f56e-270">有时你可能想要的 F # 使用者名称中一种样式的某些内容 (例如，采用小写，使其显示的是静态成员就像它是模块绑定函数)，但它会编译成程序集时产生的名称不同的样式。</span><span class="sxs-lookup"><span data-stu-id="0f56e-270">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="0f56e-271">你可以使用`[<CompiledName>]`属性的非 F # 代码使用程序集提供不同的样式。</span><span class="sxs-lookup"><span data-stu-id="0f56e-271">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="0f56e-272">通过使用`[<CompiledName>]`，你可用于非 F # 使用者的程序集的.NET 命名约定。</span><span class="sxs-lookup"><span data-stu-id="0f56e-272">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="0f56e-273">如果这样做将提供更简单的 API，使用方法重载成员函数</span><span class="sxs-lookup"><span data-stu-id="0f56e-273">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="0f56e-274">方法重载是功能强大的工具，用于简化一个 API，可能需要执行类似的功能，但具有不同的选项或参数。</span><span class="sxs-lookup"><span data-stu-id="0f56e-274">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="0f56e-275">在 F # 中，是更常见的是上的参数数目，而不是类型参数的重载。</span><span class="sxs-lookup"><span data-stu-id="0f56e-275">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="0f56e-276">如果这些类型的设计非常可能会不断变化，则隐藏的表示形式记录和联合类型</span><span class="sxs-lookup"><span data-stu-id="0f56e-276">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="0f56e-277">避免泄露具体对象表示形式。</span><span class="sxs-lookup"><span data-stu-id="0f56e-277">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="0f56e-278">例如的具体表示形式<xref:System.DateTime>通过.NET 库设计的外部的公共 API 不显示值。</span><span class="sxs-lookup"><span data-stu-id="0f56e-278">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="0f56e-279">在运行时，公共语言运行时知道将执行中使用的提交的实现。</span><span class="sxs-lookup"><span data-stu-id="0f56e-279">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="0f56e-280">但是，已编译的代码不本身选取对具体的表示形式的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="0f56e-280">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="0f56e-281">避免实现继承用于扩展性</span><span class="sxs-lookup"><span data-stu-id="0f56e-281">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="0f56e-282">在 F # 中，实现继承很少使用。</span><span class="sxs-lookup"><span data-stu-id="0f56e-282">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="0f56e-283">此外，继承层次结构通常是将复杂且难以实现，若要更改新要求到达时。</span><span class="sxs-lookup"><span data-stu-id="0f56e-283">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="0f56e-284">继承的实现仍在 F # 的兼容性和极少数情况下，这是最佳的解决方案到问题，但多态性，如接口的实现的设计时，应在 F # 程序中查找其他方法。</span><span class="sxs-lookup"><span data-stu-id="0f56e-284">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="0f56e-285">函数和成员的签名</span><span class="sxs-lookup"><span data-stu-id="0f56e-285">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="0f56e-286">返回值返回少量的多个不相关的值时使用元组</span><span class="sxs-lookup"><span data-stu-id="0f56e-286">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="0f56e-287">下面是在返回类型中使用一个元组的一个很好示例：</span><span class="sxs-lookup"><span data-stu-id="0f56e-287">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="0f56e-288">有关返回类型包含许多组件，或如果组件将与单个身份实体，请考虑使用命名的类型而不元组。</span><span class="sxs-lookup"><span data-stu-id="0f56e-288">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="0f56e-289">使用`Async<T>`为在 F # API 边界进行异步编程</span><span class="sxs-lookup"><span data-stu-id="0f56e-289">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="0f56e-290">如果没有相应的同步操作名为`Operation`返回`T`，则应命名为异步操作`AsyncOperation`如果它返回`Async<T>`或`OperationAsync`如果它返回`Task<T>`。</span><span class="sxs-lookup"><span data-stu-id="0f56e-290">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="0f56e-291">常用的.NET 类型来公开 Begin/End 方法，请考虑使用`Async.FromBeginEnd`作为外观以提供对这些.NET Api 的 F # 异步编程模型编写扩展方法。</span><span class="sxs-lookup"><span data-stu-id="0f56e-291">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

```fsharp
type SomeType =
    member this.Compute(x:int) : int =
        ...
    member this.AsyncCompute(x:int) : Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a><span data-ttu-id="0f56e-292">异常</span><span class="sxs-lookup"><span data-stu-id="0f56e-292">Exceptions</span></span>

<span data-ttu-id="0f56e-293">例外情况是在.NET; 异常也就是说，它们应不频繁发生在运行时。</span><span class="sxs-lookup"><span data-stu-id="0f56e-293">Exceptions are exceptional in .NET; that is, they should not occur frequently at runtime.</span></span> <span data-ttu-id="0f56e-294">当他们执行时，它们包含的信息是有价值。</span><span class="sxs-lookup"><span data-stu-id="0f56e-294">When they do, the information they contain is valuable.</span></span> <span data-ttu-id="0f56e-295">例外情况是核心的.NET; 第一类概念it 因此如下所示，相应的异常的应用程序应使用的组件的接口的设计的一部分。</span><span class="sxs-lookup"><span data-stu-id="0f56e-295">Exceptions are a core first class concept of .NET; it hence follows that appropriate application of the Exceptions should be used as part of the design of the interface of a component.</span></span>

#### <a name="follow-the-net-guidelines-for-exceptions"></a><span data-ttu-id="0f56e-296">遵循异常的.NET 指南</span><span class="sxs-lookup"><span data-stu-id="0f56e-296">Follow the .NET guidelines for exceptions</span></span>

<span data-ttu-id="0f56e-297">[.NET 库设计准则](../../standard/design-guidelines/exceptions.md)为极好的建议提供有关使用的上下文中的所有.NET 编程的异常。</span><span class="sxs-lookup"><span data-stu-id="0f56e-297">The [.NET Library Design Guidelines](../../standard/design-guidelines/exceptions.md) give excellent advice on the use of exceptions in the context of all .NET programming.</span></span> <span data-ttu-id="0f56e-298">某些这些准则如下所示：</span><span class="sxs-lookup"><span data-stu-id="0f56e-298">Some of these guidelines are as follows:</span></span>

* <span data-ttu-id="0f56e-299">请在正常控制流中使用异常。</span><span class="sxs-lookup"><span data-stu-id="0f56e-299">Do not use exceptions for normal flow of control.</span></span> <span data-ttu-id="0f56e-300">虽然在 OCaml 等语言中经常使用此技术，它 bug 容易，并可能在.NET 效率很低。</span><span class="sxs-lookup"><span data-stu-id="0f56e-300">Although this technique is often used in languages such as OCaml, it is bug-prone and can be inefficient on .NET.</span></span> <span data-ttu-id="0f56e-301">相反，请考虑返回`None`选项值以指示失败引起的是一种常见的或预期的情况。</span><span class="sxs-lookup"><span data-stu-id="0f56e-301">Instead, consider returning a `None` option value to indicate a failure that is a common or expected occurrence.</span></span>

* <span data-ttu-id="0f56e-302">记录错误地使用了函数时，由你的组件引发的异常。</span><span class="sxs-lookup"><span data-stu-id="0f56e-302">Document exceptions thrown by your components when a function is used incorrectly.</span></span>

* <span data-ttu-id="0f56e-303">如果可能，采用 System 命名空间中的现有异常。</span><span class="sxs-lookup"><span data-stu-id="0f56e-303">Where possible, employ existing exceptions from the System namespaces.</span></span> <span data-ttu-id="0f56e-304">避免<xref:System.ApplicationException>，不过。</span><span class="sxs-lookup"><span data-stu-id="0f56e-304">Avoid <xref:System.ApplicationException>, though.</span></span>

* <span data-ttu-id="0f56e-305">不会引发<xref:System.Exception>时它将在其中转义到用户代码。</span><span class="sxs-lookup"><span data-stu-id="0f56e-305">Do not throw <xref:System.Exception> when it will escape to user code.</span></span> <span data-ttu-id="0f56e-306">这包括避免使用`failwith`， `failwithf`，这是方便函数在脚本中使用而使正在开发的代码，但应从 F # 库代码而引发的更具体的异常类型中移除。</span><span class="sxs-lookup"><span data-stu-id="0f56e-306">This includes avoiding the use of `failwith`, `failwithf`, which are handy functions for use in scripting and for code under development, but should be removed from F# library code in favor of throwing a more specific exception type.</span></span>

* <span data-ttu-id="0f56e-307">使用`nullArg`， `invalidArg`，和`invalidOp`作为机制引发<xref:System.ArgumentNullException>， <xref:System.ArgumentException>，和<xref:System.InvalidOperationException>在适当的时候。</span><span class="sxs-lookup"><span data-stu-id="0f56e-307">Use `nullArg`, `invalidArg`, and `invalidOp` as the mechanism to throw <xref:System.ArgumentNullException>, <xref:System.ArgumentException>, and <xref:System.InvalidOperationException> when appropriate.</span></span>

#### <a name="consider-using-option-values-for-return-types-when-failure-is-not-an-exceptional-scenario"></a><span data-ttu-id="0f56e-308">请考虑使用返回类型的选项值时的失败不是异常的方案</span><span class="sxs-lookup"><span data-stu-id="0f56e-308">Consider using option values for return types when failure is not an exceptional scenario</span></span>

<span data-ttu-id="0f56e-309">异常的.NET 方法是，它们应是"异常";也就是说，它们应出现频率相对较低。</span><span class="sxs-lookup"><span data-stu-id="0f56e-309">The .NET approach to exceptions is that they should be “exceptional”; that is, they should occur relatively infrequently.</span></span> <span data-ttu-id="0f56e-310">但是，某些操作 （例如，搜索表） 可能会经常失败。</span><span class="sxs-lookup"><span data-stu-id="0f56e-310">However, some operations (for example, searching a table) may fail frequently.</span></span> <span data-ttu-id="0f56e-311">F # 选项值是表示这些操作的返回类型的极佳途径。</span><span class="sxs-lookup"><span data-stu-id="0f56e-311">F# option values are an excellent way to represent the return types of these operations.</span></span> <span data-ttu-id="0f56e-312">这些操作通常开头的名称前缀"try":</span><span class="sxs-lookup"><span data-stu-id="0f56e-312">These operations conventionally start with the name prefix “try”:</span></span>

```fsharp
// bad: throws exception if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// bad: returns -1 if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// good: returns None if no element meets criteria
member this.TryFindFirstIndex(pred : 'T -> bool) : int option =
    ...
```

### <a name="extension-members"></a><span data-ttu-id="0f56e-313">扩展成员</span><span class="sxs-lookup"><span data-stu-id="0f56e-313">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="0f56e-314">仔细应用 F # 中的 F # 扩展成员-到-F # 组件</span><span class="sxs-lookup"><span data-stu-id="0f56e-314">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="0f56e-315">F # 扩展成员通常只应与在使用其模式的大多数类型相关联的内部操作的闭包中的操作。</span><span class="sxs-lookup"><span data-stu-id="0f56e-315">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="0f56e-316">一种常见用途是提供的 Api，对 F # 更惯例为各种.NET 类型：</span><span class="sxs-lookup"><span data-stu-id="0f56e-316">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="0f56e-317">联合类型</span><span class="sxs-lookup"><span data-stu-id="0f56e-317">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="0f56e-318">使用可区分的联合而不是类层次结构树结构数据</span><span class="sxs-lookup"><span data-stu-id="0f56e-318">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="0f56e-319">树形结构是以递归方式定义。</span><span class="sxs-lookup"><span data-stu-id="0f56e-319">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="0f56e-320">这是繁琐利用继承，但与可区分联合简洁。</span><span class="sxs-lookup"><span data-stu-id="0f56e-320">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="0f56e-321">表示与可区分联合的树式数据还允许你可以受益于 exhaustiveness 在模式匹配。</span><span class="sxs-lookup"><span data-stu-id="0f56e-321">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="0f56e-322">使用`[<RequireQualifiedAccess>]`上其大小写的名称并不足够唯一的联合类型</span><span class="sxs-lookup"><span data-stu-id="0f56e-322">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="0f56e-323">您可能发现自己位于相同的名称其中是不同的元素，如可区分联合用例的最佳名称的域。</span><span class="sxs-lookup"><span data-stu-id="0f56e-323">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="0f56e-324">你可以使用`[<RequireQualifiedAccess>]`若要以避免触发由于隐藏依赖于排序的令人困惑错误区分大小写的名称`open`语句</span><span class="sxs-lookup"><span data-stu-id="0f56e-324">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="0f56e-325">如果这些类型的设计非常可能会不断变化，则隐藏二进制兼容的 Api 可区分联合表示形式</span><span class="sxs-lookup"><span data-stu-id="0f56e-325">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="0f56e-326">联合类型依赖于 F # 模式匹配窗体简洁的编程模型。</span><span class="sxs-lookup"><span data-stu-id="0f56e-326">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="0f56e-327">如前所述，应避免泄露具体数据表示形式，如果这些类型的设计非常可能会不断变化。</span><span class="sxs-lookup"><span data-stu-id="0f56e-327">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="0f56e-328">例如的表示形式可区分联合可以隐藏使用私有或内部声明，或使用签名文件。</span><span class="sxs-lookup"><span data-stu-id="0f56e-328">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="0f56e-329">如果不加选择地显示可区分的联合，则可能很难进行版本你的库而不会破坏用户代码。</span><span class="sxs-lookup"><span data-stu-id="0f56e-329">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="0f56e-330">相反，请考虑泄露一个或多个活动的模式，以允许你类型的值针对的模式匹配。</span><span class="sxs-lookup"><span data-stu-id="0f56e-330">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="0f56e-331">活动模式提供了另一种方法为提供同时可避免直接公开 F # 联合类型匹配的模式的 F # 使用者。</span><span class="sxs-lookup"><span data-stu-id="0f56e-331">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="0f56e-332">内联函数和成员约束</span><span class="sxs-lookup"><span data-stu-id="0f56e-332">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="0f56e-333">定义中使用内联函数的隐式的成员约束和静态解析的泛型类型的泛型数值算法</span><span class="sxs-lookup"><span data-stu-id="0f56e-333">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="0f56e-334">算术成员约束和 F # 比较约束是一种标准 F # 编程。</span><span class="sxs-lookup"><span data-stu-id="0f56e-334">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="0f56e-335">例如，考虑以下代码：</span><span class="sxs-lookup"><span data-stu-id="0f56e-335">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="0f56e-336">此函数的类型如下所示：</span><span class="sxs-lookup"><span data-stu-id="0f56e-336">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="0f56e-337">这是一个数学库中的公共 API 的合适的函数。</span><span class="sxs-lookup"><span data-stu-id="0f56e-337">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="0f56e-338">避免使用成员约束模拟类型类和鸭子类型化</span><span class="sxs-lookup"><span data-stu-id="0f56e-338">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="0f56e-339">可以模拟"回避键入"使用 F # 成员约束。</span><span class="sxs-lookup"><span data-stu-id="0f56e-339">It is possible to simulate “duck typing” using F# member constraints.</span></span> <span data-ttu-id="0f56e-340">但是，成员，请使用此应不在常规使用 F # 中-到-F # 库设计。</span><span class="sxs-lookup"><span data-stu-id="0f56e-340">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="0f56e-341">这是因为库设计基于不熟悉或非标准的隐式约束可能会导致用户代码可以灵活地绑定到一个特定的框架模式。</span><span class="sxs-lookup"><span data-stu-id="0f56e-341">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="0f56e-342">此外，还有很可能会使用大量的这种方式中的成员约束可能会很长的编译时间。</span><span class="sxs-lookup"><span data-stu-id="0f56e-342">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="0f56e-343">运算符定义</span><span class="sxs-lookup"><span data-stu-id="0f56e-343">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="0f56e-344">避免定义自定义的符号运算符</span><span class="sxs-lookup"><span data-stu-id="0f56e-344">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="0f56e-345">自定义运算符是基本在某些情况下，大量的实现代码中的非常有用符号设备。</span><span class="sxs-lookup"><span data-stu-id="0f56e-345">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="0f56e-346">对于的库的新用户，命名的函数通常是使用起来更为简便。</span><span class="sxs-lookup"><span data-stu-id="0f56e-346">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="0f56e-347">此外，自定义的符号运算符可以将其硬到文档中，并且用户找到它更难查找运算符，由于 IDE 和搜索引擎中的现有限制的帮助。</span><span class="sxs-lookup"><span data-stu-id="0f56e-347">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="0f56e-348">因此，最好发布你的功能作为命名的函数和成员，并仅当符号好处超过文档并认知开销，让它们此外公开此功能的运算符。</span><span class="sxs-lookup"><span data-stu-id="0f56e-348">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="0f56e-349">度量单位</span><span class="sxs-lookup"><span data-stu-id="0f56e-349">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="0f56e-350">仔细使用的度量值的单位来实现 F # 代码中添加的类型安全</span><span class="sxs-lookup"><span data-stu-id="0f56e-350">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="0f56e-351">查看其他.NET 语言时，将清除的部门的度量值的附加键入的信息。</span><span class="sxs-lookup"><span data-stu-id="0f56e-351">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="0f56e-352">请注意，.NET 组件、 工具和反射将看到类型 san 单位。</span><span class="sxs-lookup"><span data-stu-id="0f56e-352">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="0f56e-353">例如，C# 使用者将看到`float`而非`float<kg>`。</span><span class="sxs-lookup"><span data-stu-id="0f56e-353">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="0f56e-354">类型缩写</span><span class="sxs-lookup"><span data-stu-id="0f56e-354">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="0f56e-355">仔细使用类型缩写来简化 F # 代码</span><span class="sxs-lookup"><span data-stu-id="0f56e-355">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="0f56e-356">.NET 组件、 工具和反射看不到类型的缩写的名称。</span><span class="sxs-lookup"><span data-stu-id="0f56e-356">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="0f56e-357">长时间使用的类型缩写还可以显示变得更加复杂比它实际上是，其无法混淆使用者域。</span><span class="sxs-lookup"><span data-stu-id="0f56e-357">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="0f56e-358">避免其成员和属性应本质上可用的正在缩写的类型不同的公共类型的类型缩写</span><span class="sxs-lookup"><span data-stu-id="0f56e-358">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="0f56e-359">在这种情况下，正在缩写的类型将显示有关正在定义的实际类型表示的过多信息。</span><span class="sxs-lookup"><span data-stu-id="0f56e-359">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="0f56e-360">相反，请考虑包装类类型或单用例可区分的联合中的缩写 （或时性能至关重要，请考虑使用结构类型包装缩写）。</span><span class="sxs-lookup"><span data-stu-id="0f56e-360">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="0f56e-361">例如，它很容易定义为 F # 映射的一种特殊情况多地图，例如：</span><span class="sxs-lookup"><span data-stu-id="0f56e-361">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="0f56e-362">但是，此类型上的逻辑点表示法操作不是在地图上的操作相同 – 例如，它位于合理查找运算符映射。[键] 返回空列表如果该键不在字典中，而不是引发异常。</span><span class="sxs-lookup"><span data-stu-id="0f56e-362">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="0f56e-363">适用于从其他.NET 语言中使用的库的准则</span><span class="sxs-lookup"><span data-stu-id="0f56e-363">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="0f56e-364">在设计时用于其他.NET 语言使用的库，请务必遵守[.NET 库设计准则](../../standard/design-guidelines/index.md)。</span><span class="sxs-lookup"><span data-stu-id="0f56e-364">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="0f56e-365">在此文档中，这些库都标记为香草.NET 库，而不是 F #-面向使用 F # 库构造不受限制。</span><span class="sxs-lookup"><span data-stu-id="0f56e-365">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="0f56e-366">设计香草.NET 库意味着通过最小化使用 F # 提供熟悉且惯用 Api 与.NET Framework 的其余部分一致的公共 API 中的特定构造。</span><span class="sxs-lookup"><span data-stu-id="0f56e-366">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="0f56e-367">规则将在以下各节中介绍。</span><span class="sxs-lookup"><span data-stu-id="0f56e-367">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="0f56e-368">Namespace 和类型的设计，（对于从其他.NET 语言中使用的库）</span><span class="sxs-lookup"><span data-stu-id="0f56e-368">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="0f56e-369">适用于你的组件的公共 API 的.NET 命名约定</span><span class="sxs-lookup"><span data-stu-id="0f56e-369">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="0f56e-370">请特别注意到使用缩写的名称和.NET 大小写准则。</span><span class="sxs-lookup"><span data-stu-id="0f56e-370">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="0f56e-371">使用命名空间、 类型和成员作为你的组件的主要组织结构</span><span class="sxs-lookup"><span data-stu-id="0f56e-371">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="0f56e-372">包含公共的功能的所有文件应都开头`namespace`声明和命名空间中的唯一的面向公众的实体应是类型。</span><span class="sxs-lookup"><span data-stu-id="0f56e-372">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="0f56e-373">不要使用 F # 模块。</span><span class="sxs-lookup"><span data-stu-id="0f56e-373">Do not use F# modules.</span></span>

<span data-ttu-id="0f56e-374">使用非公共模块保存实现代码、 实用程序类型和实用工具函数。</span><span class="sxs-lookup"><span data-stu-id="0f56e-374">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="0f56e-375">静态类型应优先模块，因为它们允许的未来发展的 api 用于重载和其他不能在 F # 模块内使用的.NET API 设计概念。</span><span class="sxs-lookup"><span data-stu-id="0f56e-375">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="0f56e-376">例如，替代以下的公共 API:</span><span class="sxs-lookup"><span data-stu-id="0f56e-376">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="0f56e-377">请考虑改为：</span><span class="sxs-lookup"><span data-stu-id="0f56e-377">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="0f56e-378">如果类型的设计不会不断发展，在香草.NET Api 中使用 F # 记录类型</span><span class="sxs-lookup"><span data-stu-id="0f56e-378">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="0f56e-379">F # 记录类型编译为一个简单的.NET 类。</span><span class="sxs-lookup"><span data-stu-id="0f56e-379">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="0f56e-380">这些是适用于 Api 中的某些简单、 稳定的类型。</span><span class="sxs-lookup"><span data-stu-id="0f56e-380">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="0f56e-381">你应考虑使用`[<NoEquality>]`和`[<NoComparison>]`属性来取消自动生成的接口。</span><span class="sxs-lookup"><span data-stu-id="0f56e-381">You should consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="0f56e-382">此外避免使用与这些公开的公共字段的香草.NET Api 中的可变记录字段。</span><span class="sxs-lookup"><span data-stu-id="0f56e-382">Also avoid using mutable record fields in vanilla .NET APIs as these exposes a public field.</span></span> <span data-ttu-id="0f56e-383">应始终考虑是否的类将提供更灵活的 api 选项未来变化情况。</span><span class="sxs-lookup"><span data-stu-id="0f56e-383">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="0f56e-384">例如，下面的 F # 代码公开的公共 API 的 C# 使用者：</span><span class="sxs-lookup"><span data-stu-id="0f56e-384">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="0f56e-385">F # 中：</span><span class="sxs-lookup"><span data-stu-id="0f56e-385">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing : int
        SecondThing : string }
```

<span data-ttu-id="0f56e-386">C#：</span><span class="sxs-lookup"><span data-stu-id="0f56e-386">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="0f56e-387">隐藏的表示形式香草.NET Api 联合类型 F #</span><span class="sxs-lookup"><span data-stu-id="0f56e-387">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="0f56e-388">F # 联合类型不常用于跨组件边界进行，即使对于 F #-到-F # 编码。</span><span class="sxs-lookup"><span data-stu-id="0f56e-388">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="0f56e-389">它们是一种绝佳实现设备时在组件和库内部使用。</span><span class="sxs-lookup"><span data-stu-id="0f56e-389">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="0f56e-390">在设计时一个普通的.NET API，请考虑使用专用的声明或签名文件中隐藏的表示形式的联合类型。</span><span class="sxs-lookup"><span data-stu-id="0f56e-390">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="0f56e-391">你还可能增加使用联合表示形式内部与成员来提供所需的类型。NET 面向 API。</span><span class="sxs-lookup"><span data-stu-id="0f56e-391">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True

    /// A public member for use from C#
    member x.Evaluate =
        match x with
        | And(a,b) -> a.Evaluate && b.Evaluate
        | Not a -> not a.Evaluate
        | True -> true

    /// A public member for use from C#
    static member CreateAnd(a,b) = And(a,b)
```

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="0f56e-392">设计 GUI 和其他组件使用的框架的设计模式</span><span class="sxs-lookup"><span data-stu-id="0f56e-392">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="0f56e-393">在.NET 中，如 WinForms、 WPF 和 ASP.NET 中有可用的很多不同的框架。</span><span class="sxs-lookup"><span data-stu-id="0f56e-393">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="0f56e-394">如果您正在设计用于这些框架组件，则应使用每个命名和设计约定。</span><span class="sxs-lookup"><span data-stu-id="0f56e-394">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="0f56e-395">例如，对于 WPF 编程，采用设计的类的 WPF 设计的模式。</span><span class="sxs-lookup"><span data-stu-id="0f56e-395">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="0f56e-396">对于在用户界面编程模型，使用如事件的设计模式和基于通知的集合，如位于<xref:System.Collections.ObjectModel>。</span><span class="sxs-lookup"><span data-stu-id="0f56e-396">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="0f56e-397">（对于从其他.NET 语言中使用的库） 的对象和成员设计</span><span class="sxs-lookup"><span data-stu-id="0f56e-397">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="0f56e-398">CLIEvent 特性用于公开.NET 事件</span><span class="sxs-lookup"><span data-stu-id="0f56e-398">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="0f56e-399">构造`DelegateEvent`与特定的.NET 委托采用对象的类型和`EventArgs`(而非`Event`，只需使用`FSharpHandler`类型默认情况下的)，以便事件要发布到其他.NET 语言熟悉的方式。</span><span class="sxs-lookup"><span data-stu-id="0f56e-399">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x:int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a><span data-ttu-id="0f56e-400">公开异步操作作为方法返回.NET 任务</span><span class="sxs-lookup"><span data-stu-id="0f56e-400">Expose asynchronous operations as methods which return .NET tasks</span></span>

<span data-ttu-id="0f56e-401">在.NET 中使用任务来表示活动的异步计算。</span><span class="sxs-lookup"><span data-stu-id="0f56e-401">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="0f56e-402">任务是通常比 F # 不太组合`Async<T>`对象，因为它们表示"已经在执行"任务，不能由在一起，可以执行并行组合，或该隐藏取消信号和其他的传播用的方式上下文参数。</span><span class="sxs-lookup"><span data-stu-id="0f56e-402">Tasks are in general less compositional than F# `Async<T>` objects, since they represent “already executing” tasks and can’t be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="0f56e-403">但是，尽管此操作，请返回任务的方法是于.NET 的异步编程的标准表示。</span><span class="sxs-lookup"><span data-stu-id="0f56e-403">However, despite this, methods which return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="0f56e-404">经常将还想要接受显式取消标记：</span><span class="sxs-lookup"><span data-stu-id="0f56e-404">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="0f56e-405">使用.NET 委托类型，而不是 F # 函数类型</span><span class="sxs-lookup"><span data-stu-id="0f56e-405">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="0f56e-406">此处"F # 函数类型"意味着"箭头"类型喜欢`int -> int`。</span><span class="sxs-lookup"><span data-stu-id="0f56e-406">Here “F# function types” mean “arrow” types like `int -> int`.</span></span>

<span data-ttu-id="0f56e-407">而不是以下内容：</span><span class="sxs-lookup"><span data-stu-id="0f56e-407">Instead of this:</span></span>

```fsharp
member this.Transform(f:int->int) =
    ...
```

<span data-ttu-id="0f56e-408">执行此操作：</span><span class="sxs-lookup"><span data-stu-id="0f56e-408">Do this:</span></span>

```fsharp
member this.Transform(f:Func<int,int>) =
    ...
```

<span data-ttu-id="0f56e-409">F # 函数类型显示为`class FSharpFunc<T,U>`到其他.NET 语言，且不太适用于了解委托类型的语言功能和工具。</span><span class="sxs-lookup"><span data-stu-id="0f56e-409">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understand delegate types.</span></span> <span data-ttu-id="0f56e-410">创建面向.NET Framework 3.5 或更高版本，更高序位方法时`System.Func`和`System.Action`委托是正确的 Api 来发布可让.NET 开发人员要低冲突的方式使用这些 Api。</span><span class="sxs-lookup"><span data-stu-id="0f56e-410">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="0f56e-411">(如果目标.NET Framework 2.0，系统定义的委托类型是受限更多; 请考虑使用预定义的委托类型，例如`System.Converter<T,U>`或定义特定委托类型。)</span><span class="sxs-lookup"><span data-stu-id="0f56e-411">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="0f56e-412">另一方面，.NET 委托不自然的 F #-面向库 (请参阅在 F # 的下一步部分-面向库)。</span><span class="sxs-lookup"><span data-stu-id="0f56e-412">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="0f56e-413">因此，常见的实现策略开发香草.NET 库的更高序位方法时是以创作所有使用 F # 函数类型的实现，然后创建使用委托作为之上的实际 F # 的精简外观的公共 API实现。</span><span class="sxs-lookup"><span data-stu-id="0f56e-413">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="0f56e-414">使用 TryGetValue 模式而不是返回 F # 选项值，并首选采用 F # 选项值作为自变量的重载方法</span><span class="sxs-lookup"><span data-stu-id="0f56e-414">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="0f56e-415">使用 Api 中的 F # 选项类型性的常见模式是更好地在香草中实现使用标准.NET 的.NET Api 设计技巧。</span><span class="sxs-lookup"><span data-stu-id="0f56e-415">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="0f56e-416">而不是返回的 F # 选项值，请考虑使用 bool 返回类型以及输出参数如下所示的"TryGetValue"模式。</span><span class="sxs-lookup"><span data-stu-id="0f56e-416">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="0f56e-417">而不是采用 F # 选项值作为参数，请考虑使用方法重载或可选自变量。</span><span class="sxs-lookup"><span data-stu-id="0f56e-417">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal : byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x : int, y : int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x : int) = x

member this.ParamOverload(x : int, y : int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="0f56e-418">使用.NET 集合接口类型 IEnumerable\<T\>和 IDictionary\<键、 值\>为参数和返回值</span><span class="sxs-lookup"><span data-stu-id="0f56e-418">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="0f56e-419">避免使用的具体集合类型，如.NET 数组`T[]`，F # 类型`list<T>`，`Map<Key,Value>`和`Set<T>`，和.NET 具体集合类型，如`Dictionary<Key,Value>`。</span><span class="sxs-lookup"><span data-stu-id="0f56e-419">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="0f56e-420">.NET 库设计准则已了解有关何时使用各种集合类型，如好的建议`IEnumerable<T>`。</span><span class="sxs-lookup"><span data-stu-id="0f56e-420">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="0f56e-421">某些使用数组 (`T[]`) 是在某些情况下，在性能地面可以接受的。</span><span class="sxs-lookup"><span data-stu-id="0f56e-421">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="0f56e-422">请注意，尤其是`seq<T>`是只需 F # 别名`IEnumerable<T>`，并因此 seq 通常是一个普通的.NET API 的相应类型。</span><span class="sxs-lookup"><span data-stu-id="0f56e-422">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="0f56e-423">而不是 F # 列表：</span><span class="sxs-lookup"><span data-stu-id="0f56e-423">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names : string list) =
    ...
```

<span data-ttu-id="0f56e-424">使用 F # 序列：</span><span class="sxs-lookup"><span data-stu-id="0f56e-424">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="0f56e-425">用作唯一的一种方法的输入类型的单位类型定义一个零参数的方法，或作为唯一返回类型来定义一个返回 void 的方法</span><span class="sxs-lookup"><span data-stu-id="0f56e-425">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="0f56e-426">避免的单位类型的其他用法。</span><span class="sxs-lookup"><span data-stu-id="0f56e-426">Avoid other uses of the unit type.</span></span> <span data-ttu-id="0f56e-427">这些是很好：</span><span class="sxs-lookup"><span data-stu-id="0f56e-427">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

<span data-ttu-id="0f56e-428">这是错误的：</span><span class="sxs-lookup"><span data-stu-id="0f56e-428">This is bad:</span></span>

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="0f56e-429">检查在香草.NET API 边界上的 null 值</span><span class="sxs-lookup"><span data-stu-id="0f56e-429">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="0f56e-430">F # 实现代码往往具有较少的 null 值，由于不可变的设计模式和使用限制的 F # 类型的 null 文本。</span><span class="sxs-lookup"><span data-stu-id="0f56e-430">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="0f56e-431">其他.NET 语言通常使用 null 作为值更频繁。</span><span class="sxs-lookup"><span data-stu-id="0f56e-431">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="0f56e-432">因此，公开了一个普通的.NET API 的 F # 代码应检查在 API 边界处的 null 的参数，并防止这些值更深入地流入的 F # 实现代码。</span><span class="sxs-lookup"><span data-stu-id="0f56e-432">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="0f56e-433">`isNull`函数或在进行匹配的模式`null`模式可用。</span><span class="sxs-lookup"><span data-stu-id="0f56e-433">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="0f56e-434">避免使用元组作为返回值</span><span class="sxs-lookup"><span data-stu-id="0f56e-434">Avoid using tuples as return values</span></span>

<span data-ttu-id="0f56e-435">相反，希望返回的已命名的类型保存聚合的数据，或使用输出参数返回多个值。</span><span class="sxs-lookup"><span data-stu-id="0f56e-435">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="0f56e-436">尽管.NET 中存在的元组和结构元组 （包括 C# 语言支持的结构元组），它们将最常未提供理想和预期 API 为.NET 开发人员。</span><span class="sxs-lookup"><span data-stu-id="0f56e-436">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="0f56e-437">避免使用参数的扩充</span><span class="sxs-lookup"><span data-stu-id="0f56e-437">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="0f56e-438">请改为使用.NET 调用约定``Method(arg1,arg2,…,argN)``。</span><span class="sxs-lookup"><span data-stu-id="0f56e-438">Instead, use .NET calling conventions ``Method(arg1,arg2,…,argN)``.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="0f56e-439">提示： 如果您正在设计用于从任何.NET 语言的库，则没有任何替代的实际执行的一些实验性 C# 和 Visual Basic 编程以确保你的库"感觉右"从这些语言操作。</span><span class="sxs-lookup"><span data-stu-id="0f56e-439">Tip: If you’re designing libraries for use from any .NET language, then there’s no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="0f56e-440">你可以使用.NET 反射器和 Visual Studio 对象浏览器等工具以确保库和其文档显示按预期给开发人员。</span><span class="sxs-lookup"><span data-stu-id="0f56e-440">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="0f56e-441">附录</span><span class="sxs-lookup"><span data-stu-id="0f56e-441">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="0f56e-442">由其他.NET 语言设计的使用 F # 代码的端到端示例</span><span class="sxs-lookup"><span data-stu-id="0f56e-442">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="0f56e-443">请考虑以下类：</span><span class="sxs-lookup"><span data-stu-id="0f56e-443">Consider the following class:</span></span>

```fsharp
open System

type Point1(angle,radius) =
    new() = Point1(angle=0.0, radius=0.0)
    member x.Angle = angle
    member x.Radius = radius
    member x.Stretch(l) = Point1(angle=x.Angle, radius=x.Radius * l)
    member x.Warp(f) = Point1(angle=f(x.Angle), radius=x.Radius)
    static member Circle(n) =
        [ for i in 1..n -> Point1(angle=2.0*Math.PI/float(n), radius=1.0) ]
```

<span data-ttu-id="0f56e-444">此类的推断的 F # 个类型如下所示：</span><span class="sxs-lookup"><span data-stu-id="0f56e-444">The inferred F# type of this class is as follows:</span></span>

```fsharp
type Point1 =
    new : unit -> Point1
    new : angle:double * radius:double -> Point1
    static member Circle : n:int -> Point1 list
    member Stretch : l:double -> Point1
    member Warp : f:(double -> double) -> Point1
    member Angle : double
    member Radius : double
```

<span data-ttu-id="0f56e-445">让我们看看此 F # 类型到程序员使用其他.NET 语言的显示方式。</span><span class="sxs-lookup"><span data-stu-id="0f56e-445">Let’s take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="0f56e-446">例如，近似 C#"签名"是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0f56e-446">For example, the approximate C# “signature” is as follows:</span></span>

```csharp
// C# signature for the unadjusted Point1 class
public class Point1
{
    public Point1();

    public Point1(double angle, double radius);

    public static Microsoft.FSharp.Collections.List<Point1> Circle(int count);

    public Point1 Stretch(double factor);

    public Point1 Warp(Microsoft.FSharp.Core.FastFunc<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

<span data-ttu-id="0f56e-447">有一些重要事项需要注意有关 F # 如何表示此处构造。</span><span class="sxs-lookup"><span data-stu-id="0f56e-447">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="0f56e-448">例如：</span><span class="sxs-lookup"><span data-stu-id="0f56e-448">For example:</span></span>

* <span data-ttu-id="0f56e-449">已保留元数据，例如自变量名称。</span><span class="sxs-lookup"><span data-stu-id="0f56e-449">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="0f56e-450">F # 方法采用两个参数成为采用两个参数的 C# 方法。</span><span class="sxs-lookup"><span data-stu-id="0f56e-450">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="0f56e-451">函数和列表会变得对 F # 库中的相应类型的引用。</span><span class="sxs-lookup"><span data-stu-id="0f56e-451">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="0f56e-452">下面的代码演示如何调整此代码，以考虑以下事项。</span><span class="sxs-lookup"><span data-stu-id="0f56e-452">The following code shows how to adjust this code to take these things into account.</span></span>

```fsharp
namespace SuperDuperFSharpLibrary.Types

type RadialPoint(angle:double, radius:double) =

    /// Return a point at the origin
    new() = RadialPoint(angle=0.0, radius=0.0)

    /// The angle to the point, from the x-axis
    member x.Angle = angle

    /// The distance to the point, from the origin
    member x.Radius = radius

    /// Return a new point, with radius multiplied by the given factor
    member x.Stretch(factor) =
        RadialPoint(angle=angle, radius=radius * factor)

    /// Return a new point, with angle transformed by the function
    member x.Warp(transform:Func<_,_>) =
        RadialPoint(angle=transform.Invoke angle, radius=radius)

    /// Return a sequence of points describing an approximate circle using
    /// the given count of points
    static member Circle(count) =
        seq { for i in 1..count ->
                RadialPoint(angle=2.0*Math.PI/float(count), radius=1.0) }
```

<span data-ttu-id="0f56e-453">推断的 F # 代码的类型，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0f56e-453">The inferred F# type of the code is as follows:</span></span>

```fsharp
type RadialPoint =
    new : unit -> RadialPoint
    new : angle:double * radius:double -> RadialPoint
    static member Circle : count:int -> seq<RadialPoint>
    member Stretch : factor:double -> RadialPoint
    member Warp : transform:System.Func<double,double> -> RadialPoint
    member Angle : double
    member Radius : double
```

<span data-ttu-id="0f56e-454">C# 签名现，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0f56e-454">The C# signature is now as follows:</span></span>

```csharp
public class RadialPoint
{
    public RadialPoint();

    public RadialPoint(double angle, double radius);

    public static System.Collections.Generic.IEnumerable<RadialPoint> Circle(int count);

    public RadialPoint Stretch(double factor);

    public RadialPoint Warp(System.Func<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

<span data-ttu-id="0f56e-455">修复进行准备以便使用此类型，因为香草.NET 库的一部分，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0f56e-455">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="0f56e-456">调整多个名称： `Point1`， `n`， `l`，和`f`变为`RadialPoint`， `count`， `factor`，和`transform`分别。</span><span class="sxs-lookup"><span data-stu-id="0f56e-456">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="0f56e-457">使用返回类型为`seq<RadialPoint>`而不是`RadialPoint list`通过更改列表构造使用`[ ... ]`序列构造使用`IEnumerable<RadialPoint>`。</span><span class="sxs-lookup"><span data-stu-id="0f56e-457">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="0f56e-458">使用.NET 委托类型`System.Func`而不使用 F # 函数类型。</span><span class="sxs-lookup"><span data-stu-id="0f56e-458">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="0f56e-459">这使得更不用去涉猎，若要在 C# 代码中使用。</span><span class="sxs-lookup"><span data-stu-id="0f56e-459">This makes it far nicer to consume in C# code.</span></span>
