---
title: F# 组件设计准则
description: '了解用于编写用于其他调用方的使用的 F # 组件的准则。'
ms.date: 05/14/2018
ms.openlocfilehash: 590bda0660d54ea73c590d31e694f3d499e0fd9f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209131"
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="1fc5e-103">F# 组件设计准则</span><span class="sxs-lookup"><span data-stu-id="1fc5e-103">F# component design guidelines</span></span>

<span data-ttu-id="1fc5e-104">本文档是针对 F # 编程的一组组件设计准则，基于 F # 组件设计准则、v14、Microsoft Research 以及 F # Software Foundation 最初特选和维护的版本。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and a version that was originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="1fc5e-105">本文档假设你熟悉 F # 编程。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="1fc5e-106">很多感谢在本指南的各个版本上对 F # 社区进行贡献和有用的反馈。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="1fc5e-107">概述</span><span class="sxs-lookup"><span data-stu-id="1fc5e-107">Overview</span></span>

<span data-ttu-id="1fc5e-108">本文档介绍与 F # 组件的设计和编码相关的一些问题。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="1fc5e-109">组件可以表示以下任意内容：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="1fc5e-110">F # 项目中的一个层，它在该项目中具有外部使用者。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="1fc5e-111">用于跨程序集边界的 F # 代码使用的库。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="1fc5e-112">用于跨程序集边界使用任意 .NET 语言的库。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="1fc5e-113">一个库，用于通过包存储库（如[NuGet](https://nuget.org)）进行分发。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="1fc5e-114">本文中所述的方法遵循[良好 F # 代码的五个原则](index.md#five-principles-of-good-f-code)，并根据需要使用函数和对象编程。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="1fc5e-115">无论采用哪种方法，组件和库设计器都在尝试创建最能由开发人员使用的 API 时，会面临许多实际和 prosaic 的问题。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="1fc5e-116">[.Net 库设计准则](../../standard/design-guidelines/index.md)的 Conscientious 应用程序将指导你创建一组一致的 api，这些 api 可供使用。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="1fc5e-117">一般指南</span><span class="sxs-lookup"><span data-stu-id="1fc5e-117">General guidelines</span></span>

<span data-ttu-id="1fc5e-118">无论库的目标受众如何，都有一些适用于 F # 库的通用准则。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="1fc5e-119">了解 .NET 库设计准则</span><span class="sxs-lookup"><span data-stu-id="1fc5e-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="1fc5e-120">无论你正在执行哪种 F # 编码，都有必要了解[.Net 库设计准则](../../standard/design-guidelines/index.md)的工作知识。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="1fc5e-121">大多数其他 F # 和 .NET 程序员都将熟悉这些准则，并且预计 .NET 代码符合这些准则。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="1fc5e-122">.NET 库设计指南提供了有关命名、设计类和接口、成员设计（属性、方法、事件等）的一般指导，并是各种设计指导的有用的第一引用。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="1fc5e-123">向代码添加 XML 文档注释</span><span class="sxs-lookup"><span data-stu-id="1fc5e-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="1fc5e-124">有关公共 Api 的 XML 文档可确保用户可以在使用这些类型和成员时获得出色的 Intellisense 和 Quickinfo，并为库启用生成文档文件。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-124">XML documentation on public APIs ensures that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="1fc5e-125">请参阅[Xml 文档](../language-reference/xml-documentation.md)，了解可用于 xmldoc 注释中的其他标记的各种 xml 标记。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo: otherPoint:Point -> float
```

<span data-ttu-id="1fc5e-126">您可以使用 short 形式 XML 注释（ `/// comment` ）或标准 xml 注释（ `///<summary>comment</summary>` ）。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="1fc5e-127">请考虑对稳定库和组件 Api 使用显式签名文件（. fsi.exe）</span><span class="sxs-lookup"><span data-stu-id="1fc5e-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="1fc5e-128">在 F # 库中使用显式签名文件可提供公共 API 的简洁摘要，有助于确保了解库的完整公共表面，并提供公共文档和内部实现细节之间的完全分离。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which helps to ensure that you know the full public surface of your library, and provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="1fc5e-129">签名文件通过要求在实现和签名文件中进行更改，增加了更改公共 API 的摩擦。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-129">Signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="1fc5e-130">因此，通常只应在 API 变为日臻完善并且不再需要明显更改时才引入签名文件。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="1fc5e-131">始终遵循在 .NET 中使用字符串的最佳做法</span><span class="sxs-lookup"><span data-stu-id="1fc5e-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="1fc5e-132">遵循[在 .net 指南中使用字符串的最佳做法](../../standard/base-types/best-practices-strings.md)。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="1fc5e-133">特别是，应始终在转换和比较字符串（如果适用）时明确声明*区域性意图*。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="1fc5e-134">面向 F # 的库的准则</span><span class="sxs-lookup"><span data-stu-id="1fc5e-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="1fc5e-135">本部分提供有关开发面向公共 F # 的库的建议;也就是说，库公开旨在供 F # 开发人员使用的公共 Api。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="1fc5e-136">有多种适用于 F # 的库设计建议。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="1fc5e-137">如果没有遵循的具体建议，.NET 库设计指导原则就是回退指导。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="1fc5e-138">命名约定</span><span class="sxs-lookup"><span data-stu-id="1fc5e-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="1fc5e-139">使用 .NET 命名和大小写约定</span><span class="sxs-lookup"><span data-stu-id="1fc5e-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="1fc5e-140">下表遵循 .NET 命名和大小写约定。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="1fc5e-141">还增加了 F # 构造。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="1fc5e-142">构造</span><span class="sxs-lookup"><span data-stu-id="1fc5e-142">Construct</span></span> | <span data-ttu-id="1fc5e-143">案例</span><span class="sxs-lookup"><span data-stu-id="1fc5e-143">Case</span></span> | <span data-ttu-id="1fc5e-144">组成部分</span><span class="sxs-lookup"><span data-stu-id="1fc5e-144">Part</span></span> | <span data-ttu-id="1fc5e-145">示例</span><span class="sxs-lookup"><span data-stu-id="1fc5e-145">Examples</span></span> | <span data-ttu-id="1fc5e-146">注释</span><span class="sxs-lookup"><span data-stu-id="1fc5e-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="1fc5e-147">具体类型</span><span class="sxs-lookup"><span data-stu-id="1fc5e-147">Concrete types</span></span> | <span data-ttu-id="1fc5e-148">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1fc5e-148">PascalCase</span></span> | <span data-ttu-id="1fc5e-149">名词/形容词</span><span class="sxs-lookup"><span data-stu-id="1fc5e-149">Noun/ adjective</span></span> | <span data-ttu-id="1fc5e-150">List、Double、Complex</span><span class="sxs-lookup"><span data-stu-id="1fc5e-150">List, Double, Complex</span></span> | <span data-ttu-id="1fc5e-151">具体类型为结构、类、枚举、委托、记录和联合。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="1fc5e-152">尽管类型名称在 OCaml 中采用小写形式，但 F # 采用了用于类型的 .NET 命名方案。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="1fc5e-153">DLL</span><span class="sxs-lookup"><span data-stu-id="1fc5e-153">DLLs</span></span>           | <span data-ttu-id="1fc5e-154">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1fc5e-154">PascalCase</span></span> |                 | <span data-ttu-id="1fc5e-155">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="1fc5e-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="1fc5e-156">联合标记</span><span class="sxs-lookup"><span data-stu-id="1fc5e-156">Union tags</span></span>     | <span data-ttu-id="1fc5e-157">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1fc5e-157">PascalCase</span></span> | <span data-ttu-id="1fc5e-158">名词</span><span class="sxs-lookup"><span data-stu-id="1fc5e-158">Noun</span></span> | <span data-ttu-id="1fc5e-159">部分、添加、成功</span><span class="sxs-lookup"><span data-stu-id="1fc5e-159">Some, Add, Success</span></span> | <span data-ttu-id="1fc5e-160">不要在公共 Api 中使用前缀。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="1fc5e-161">（可选）在内部使用前缀，如`type Teams = TAlpha | TBeta | TDelta.`</span><span class="sxs-lookup"><span data-stu-id="1fc5e-161">Optionally use a prefix when internal, such as `type Teams = TAlpha | TBeta | TDelta.`</span></span> |
| <span data-ttu-id="1fc5e-162">事件</span><span class="sxs-lookup"><span data-stu-id="1fc5e-162">Event</span></span>          | <span data-ttu-id="1fc5e-163">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1fc5e-163">PascalCase</span></span> | <span data-ttu-id="1fc5e-164">Verb</span><span class="sxs-lookup"><span data-stu-id="1fc5e-164">Verb</span></span> | <span data-ttu-id="1fc5e-165">ValueChanged/ValueChanging</span><span class="sxs-lookup"><span data-stu-id="1fc5e-165">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="1fc5e-166">例外</span><span class="sxs-lookup"><span data-stu-id="1fc5e-166">Exceptions</span></span>     | <span data-ttu-id="1fc5e-167">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1fc5e-167">PascalCase</span></span> |      | <span data-ttu-id="1fc5e-168">WebException</span><span class="sxs-lookup"><span data-stu-id="1fc5e-168">WebException</span></span> | <span data-ttu-id="1fc5e-169">名称应以 "Exception" 结尾。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-169">Name should end with "Exception".</span></span> |
| <span data-ttu-id="1fc5e-170">字段</span><span class="sxs-lookup"><span data-stu-id="1fc5e-170">Field</span></span>          | <span data-ttu-id="1fc5e-171">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1fc5e-171">PascalCase</span></span> | <span data-ttu-id="1fc5e-172">名词</span><span class="sxs-lookup"><span data-stu-id="1fc5e-172">Noun</span></span> | <span data-ttu-id="1fc5e-173">CurrentName</span><span class="sxs-lookup"><span data-stu-id="1fc5e-173">CurrentName</span></span>  | |
| <span data-ttu-id="1fc5e-174">接口类型</span><span class="sxs-lookup"><span data-stu-id="1fc5e-174">Interface types</span></span> |  <span data-ttu-id="1fc5e-175">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1fc5e-175">PascalCase</span></span> | <span data-ttu-id="1fc5e-176">名词/形容词</span><span class="sxs-lookup"><span data-stu-id="1fc5e-176">Noun/ adjective</span></span> | <span data-ttu-id="1fc5e-177">IDisposable</span><span class="sxs-lookup"><span data-stu-id="1fc5e-177">IDisposable</span></span> | <span data-ttu-id="1fc5e-178">名称应以 "I" 开头。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-178">Name should start with "I".</span></span> |
| <span data-ttu-id="1fc5e-179">方法</span><span class="sxs-lookup"><span data-stu-id="1fc5e-179">Method</span></span> |  <span data-ttu-id="1fc5e-180">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1fc5e-180">PascalCase</span></span> |  <span data-ttu-id="1fc5e-181">Verb</span><span class="sxs-lookup"><span data-stu-id="1fc5e-181">Verb</span></span> | <span data-ttu-id="1fc5e-182">ToString</span><span class="sxs-lookup"><span data-stu-id="1fc5e-182">ToString</span></span> | |
| <span data-ttu-id="1fc5e-183">命名空间</span><span class="sxs-lookup"><span data-stu-id="1fc5e-183">Namespace</span></span> | <span data-ttu-id="1fc5e-184">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1fc5e-184">PascalCase</span></span> | | <span data-ttu-id="1fc5e-185">Fsharp.core</span><span class="sxs-lookup"><span data-stu-id="1fc5e-185">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="1fc5e-186">通常 `<Organization>.<Technology>[.<Subnamespace>]` 会使用，但如果该技术独立于组织，则删除组织。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-186">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="1fc5e-187">参数</span><span class="sxs-lookup"><span data-stu-id="1fc5e-187">Parameters</span></span> | <span data-ttu-id="1fc5e-188">camelCase</span><span class="sxs-lookup"><span data-stu-id="1fc5e-188">camelCase</span></span> | <span data-ttu-id="1fc5e-189">名词</span><span class="sxs-lookup"><span data-stu-id="1fc5e-189">Noun</span></span> |  <span data-ttu-id="1fc5e-190">类型名称，转换，范围</span><span class="sxs-lookup"><span data-stu-id="1fc5e-190">typeName, transform, range</span></span> | |
| <span data-ttu-id="1fc5e-191">let 值（内部）</span><span class="sxs-lookup"><span data-stu-id="1fc5e-191">let values (internal)</span></span> | <span data-ttu-id="1fc5e-192">camelCase 或 PascalCase</span><span class="sxs-lookup"><span data-stu-id="1fc5e-192">camelCase or PascalCase</span></span> | <span data-ttu-id="1fc5e-193">名词/动词</span><span class="sxs-lookup"><span data-stu-id="1fc5e-193">Noun/ verb</span></span> |  <span data-ttu-id="1fc5e-194">getValue，myTable</span><span class="sxs-lookup"><span data-stu-id="1fc5e-194">getValue, myTable</span></span> |
| <span data-ttu-id="1fc5e-195">let 值（外部）</span><span class="sxs-lookup"><span data-stu-id="1fc5e-195">let values (external)</span></span> | <span data-ttu-id="1fc5e-196">camelCase 或 PascalCase</span><span class="sxs-lookup"><span data-stu-id="1fc5e-196">camelCase or PascalCase</span></span> | <span data-ttu-id="1fc5e-197">名词/动词</span><span class="sxs-lookup"><span data-stu-id="1fc5e-197">Noun/verb</span></span>  | <span data-ttu-id="1fc5e-198">列出地图，日期. 今天</span><span class="sxs-lookup"><span data-stu-id="1fc5e-198">List.map, Dates.Today</span></span> | <span data-ttu-id="1fc5e-199">当遵循传统的函数设计模式时，允许绑定值通常是公共的。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-199">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="1fc5e-200">但是，当标识符可用于其他 .NET 语言时，通常使用 PascalCase。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-200">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="1fc5e-201">properties</span><span class="sxs-lookup"><span data-stu-id="1fc5e-201">Property</span></span>  | <span data-ttu-id="1fc5e-202">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1fc5e-202">PascalCase</span></span>  | <span data-ttu-id="1fc5e-203">名词/形容词</span><span class="sxs-lookup"><span data-stu-id="1fc5e-203">Noun/ adjective</span></span>  | <span data-ttu-id="1fc5e-204">IsEndOfFile，背景色</span><span class="sxs-lookup"><span data-stu-id="1fc5e-204">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="1fc5e-205">布尔值属性通常使用 Is 和应为赞成，如 IsEndOfFile 中所示，not IsNotEndOfFile。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-205">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="1fc5e-206">避免缩写</span><span class="sxs-lookup"><span data-stu-id="1fc5e-206">Avoid abbreviations</span></span>

<span data-ttu-id="1fc5e-207">.NET 准则不鼓励使用缩写（例如，"使用 `OnButtonClick` 而不是 `OnBtnClick` "）。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-207">The .NET guidelines discourage the use of abbreviations (for example, "use `OnButtonClick` rather than `OnBtnClick`").</span></span> <span data-ttu-id="1fc5e-208">常见缩写（如 `Async` "异步"）是可接受的。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-208">Common abbreviations, such as `Async` for "Asynchronous", are tolerated.</span></span> <span data-ttu-id="1fc5e-209">对于函数编程，有时会忽略此准则;例如， `List.iter` 使用 "迭代" 的缩写。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-209">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for "iterate".</span></span> <span data-ttu-id="1fc5e-210">出于此原因，在 F # 对 F # 编程中使用缩写的程度往往更高，但在公共组件设计中通常不应避免。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-210">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="1fc5e-211">避免大小写名称冲突</span><span class="sxs-lookup"><span data-stu-id="1fc5e-211">Avoid casing name collisions</span></span>

<span data-ttu-id="1fc5e-212">.NET 指导原则只是因为某些客户端语言（例如 Visual Basic）不区分大小写，因此不能使用单独的大小写。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-212">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="1fc5e-213">在合适的位置使用首字母缩写</span><span class="sxs-lookup"><span data-stu-id="1fc5e-213">Use acronyms where appropriate</span></span>

<span data-ttu-id="1fc5e-214">XML 的首字母缩写词不是缩写词，在 uncapitalized 形式（Xml）的 .NET 库中广泛使用。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-214">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="1fc5e-215">只应使用众所周知的、公认的首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-215">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="1fc5e-216">对泛型参数名称使用 PascalCase</span><span class="sxs-lookup"><span data-stu-id="1fc5e-216">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="1fc5e-217">请在公共 Api 中使用 PascalCase 作为泛型参数名称，包括面向 F # 的库。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-217">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="1fc5e-218">特别是，使用、、 `T` `U` `T1` 、适用于 `T2` 任意泛型参数的名称，并且在特定名称有意义时，对于面向 F # 的库，使用的名称如 `Key` 、 `Value` 、 `Arg` （例如 `TKey` ）。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-218">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="1fc5e-219">在 F # 模块中为公共函数和值使用 PascalCase 或 camelCase</span><span class="sxs-lookup"><span data-stu-id="1fc5e-219">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="1fc5e-220">camelCase 用于设计为使用非限定（例如）的公共函数 `invalidArg` 和 "标准集合函数" （例如，List）。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-220">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the "standard collection functions" (for example, List.map).</span></span> <span data-ttu-id="1fc5e-221">在这两种情况下，函数名称的作用与语言中的关键字非常类似。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-221">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="1fc5e-222">对象、类型和模块设计</span><span class="sxs-lookup"><span data-stu-id="1fc5e-222">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="1fc5e-223">使用命名空间或模块包含类型和模块</span><span class="sxs-lookup"><span data-stu-id="1fc5e-223">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="1fc5e-224">组件中的每个 F # 文件都应以命名空间声明或模块声明开头。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-224">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="1fc5e-225">或</span><span class="sxs-lookup"><span data-stu-id="1fc5e-225">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="1fc5e-226">使用模块和命名空间在顶层组织代码之间的差异如下：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-226">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="1fc5e-227">命名空间可以跨多个文件</span><span class="sxs-lookup"><span data-stu-id="1fc5e-227">Namespaces can span multiple files</span></span>
* <span data-ttu-id="1fc5e-228">命名空间不能包含 F # 函数，除非它们位于内部模块内</span><span class="sxs-lookup"><span data-stu-id="1fc5e-228">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="1fc5e-229">任何给定模块的代码都必须包含在单个文件中</span><span class="sxs-lookup"><span data-stu-id="1fc5e-229">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="1fc5e-230">顶级模块可以包含 F # 函数，而无需内部模块</span><span class="sxs-lookup"><span data-stu-id="1fc5e-230">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="1fc5e-231">在顶级命名空间或模块之间进行的选择会影响编译形式的代码，因此，如果您的 API 最终在 F # 代码之外使用，则将影响其他 .NET 语言的视图。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-231">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="1fc5e-232">对对象类型的内部操作使用方法和属性</span><span class="sxs-lookup"><span data-stu-id="1fc5e-232">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="1fc5e-233">使用对象时，最好确保将使用的功能作为该类型的方法和属性实现。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-233">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="1fc5e-234">不一定要在该成员中实现给定成员的大容量功能，但该功能的可耗用部分应该是。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-234">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="1fc5e-235">使用类封装可变状态</span><span class="sxs-lookup"><span data-stu-id="1fc5e-235">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="1fc5e-236">在 F # 中，只需在该状态尚未由其他语言构造（如闭包、序列表达式或异步计算）进行封装的位置执行此操作。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-236">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="1fc5e-237">使用接口对相关操作进行分组</span><span class="sxs-lookup"><span data-stu-id="1fc5e-237">Use interfaces to group related operations</span></span>

<span data-ttu-id="1fc5e-238">使用接口类型来表示一组操作。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-238">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="1fc5e-239">这是对其他选项（如函数或函数的记录的元组）的首选。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-239">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T>: preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T>: preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="1fc5e-240">首选为：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-240">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize: bool -> 'T -> string
    Deserialize: bool -> string -> 'T
}
```

<span data-ttu-id="1fc5e-241">接口是 .NET 中的一流概念，你可以使用它们来实现通常会给你带来的函子。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-241">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="1fc5e-242">此外，它们还可用于将存在性类型编码到程序中，哪些功能记录不能。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-242">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-that-act-on-collections"></a><span data-ttu-id="1fc5e-243">使用模块对集合的函数进行分组</span><span class="sxs-lookup"><span data-stu-id="1fc5e-243">Use a module to group functions that act on collections</span></span>

<span data-ttu-id="1fc5e-244">定义集合类型时，请考虑 `CollectionType.map` 为新集合类型提供一组标准操作，如和 `CollectionType.iter` ）。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-244">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="1fc5e-245">如果包括此类模块，请遵循 Fsharp.core 中的函数的标准命名约定。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-245">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="1fc5e-246">使用模块将函数分组为常见的规范函数，特别是在数学和 DSL 库中</span><span class="sxs-lookup"><span data-stu-id="1fc5e-246">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="1fc5e-247">例如， `Microsoft.FSharp.Core.Operators` 是一个自动打开的顶级函数（如和）的集合 `abs` ， `sin` 由 fsharp.core 提供。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-247">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="1fc5e-248">同样，统计信息库还可能包括一个模块， `erf` 其中包含函数和 `erfc` ，此模块设计为显式或自动打开。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-248">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="1fc5e-249">请考虑使用 RequireQualifiedAccess 并认真应用 AutoOpen 属性</span><span class="sxs-lookup"><span data-stu-id="1fc5e-249">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="1fc5e-250">将 `[<RequireQualifiedAccess>]` 属性添加到模块指示可能未打开该模块，并且对该模块中的元素的引用需要显式限定访问权限。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-250">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="1fc5e-251">例如， `Microsoft.FSharp.Collections.List` 模块具有此属性。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-251">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="1fc5e-252">当模块中的函数和值有可能与其他模块中的名称冲突的名称时，这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-252">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="1fc5e-253">要求限定访问权限可大大增加库的长期可维护性和可进化性。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-253">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="1fc5e-254">将 `[<AutoOpen>]` 属性添加到模块意味着当包含命名空间打开时将打开该模块。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-254">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="1fc5e-255">`[<AutoOpen>]`特性还可以应用于程序集，以指示在引用程序集时自动打开的模块。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-255">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="1fc5e-256">例如，统计信息库**MathsHeaven**可能包含 `module MathsHeaven.Statistics.Operators` 包含函数 `erf` 和 `erfc` 。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-256">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="1fc5e-257">将此模块标记为是合理的 `[<AutoOpen>]` 。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-257">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="1fc5e-258">这意味着 `open MathsHeaven.Statistics` 还将打开此模块并将名称 `erf` 和 `erfc` 纳入范围。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-258">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="1fc5e-259">的另一个好用法 `[<AutoOpen>]` 是适用于包含扩展方法的模块。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-259">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="1fc5e-260">过度 `[<AutoOpen>]` 使用受污染无法命名空间，并且应谨慎使用特性。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-260">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="1fc5e-261">对于特定域中的特定库，明智 `[<AutoOpen>]` 地使用会导致更好的可用性。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-261">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="1fc5e-262">考虑在适当的情况下使用已知运算符，在类上定义运算符成员</span><span class="sxs-lookup"><span data-stu-id="1fc5e-262">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="1fc5e-263">有时，类用于为数学构造（如矢量）建模。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-263">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="1fc5e-264">当要建模的域具有已知的运算符时，将它们定义为类的内部成员很有用。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-264">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x: float) =

    member v.X = x

    static member (*) (vector: Vector, scalar: float) = Vector(vector.X * scalar)

    static member (+) (vector1: Vector, vector2: Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="1fc5e-265">本指南对应于这些类型的常规 .NET 指导。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-265">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="1fc5e-266">但是，在 F # 编码中，这一点也很重要，因为这允许将这些类型与 F # 函数和具有成员约束的方法（如 sumBy）结合使用。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-266">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="1fc5e-267">请考虑使用 CompiledName 来提供。其他 .NET 语言使用者的网络友好名称</span><span class="sxs-lookup"><span data-stu-id="1fc5e-267">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="1fc5e-268">有时，你可能想要对 F # 使用者使用一种形式的内容（例如，小写的静态成员，使其看起来像是模块绑定函数），但在将其编译到程序集时，它具有不同的名称样式。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-268">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="1fc5e-269">您可以使用 `[<CompiledName>]` 属性为使用程序集的非 F # 代码提供不同的样式。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-269">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="1fc5e-270">通过使用 `[<CompiledName>]` ，可以将 .net 命名约定用于程序集的非 F # 使用者。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-270">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="1fc5e-271">如果这样做，则为成员函数使用方法重载，从而提供更简单的 API</span><span class="sxs-lookup"><span data-stu-id="1fc5e-271">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="1fc5e-272">方法重载是一个功能强大的工具，用于简化可能需要执行类似功能但具有不同选项或参数的 API。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-272">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="1fc5e-273">在 F # 中，对参数数量而不是参数类型进行重载更常见。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-273">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="1fc5e-274">如果这些类型的设计可能会演化，则隐藏记录和联合类型的表示形式</span><span class="sxs-lookup"><span data-stu-id="1fc5e-274">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="1fc5e-275">避免泄漏对象的具体表示形式。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-275">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="1fc5e-276">例如，值的具体表示形式 <xref:System.DateTime> 不是由 .net 库设计的外部公共 API 显示的。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-276">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="1fc5e-277">在运行时，公共语言运行时知道将在整个执行过程中使用的已提交实现。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-277">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="1fc5e-278">不过，编译的代码本身不会选取具体表示形式的依赖项。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-278">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="1fc5e-279">避免对扩展性使用实现继承</span><span class="sxs-lookup"><span data-stu-id="1fc5e-279">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="1fc5e-280">在 F # 中，很少使用实现继承。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-280">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="1fc5e-281">此外，在新的要求到达时，继承层次结构通常很复杂且难以更改。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-281">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="1fc5e-282">在 F # 中仍存在继承实现，这是解决问题的最佳解决方案，但在设计多态性（如接口实现）时，应在 F # 程序中寻找替代方法。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-282">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="1fc5e-283">函数和成员签名</span><span class="sxs-lookup"><span data-stu-id="1fc5e-283">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="1fc5e-284">当返回的多个不相关值时，将元组用于返回值</span><span class="sxs-lookup"><span data-stu-id="1fc5e-284">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="1fc5e-285">下面是在返回类型中使用元组的一个很好的示例：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-285">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem: BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="1fc5e-286">对于包含多个组件或组件与单个可识别实体相关的返回类型，请考虑使用命名类型而不是元组。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-286">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="1fc5e-287">用于 `Async<T>` F # API 边界的异步编程</span><span class="sxs-lookup"><span data-stu-id="1fc5e-287">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="1fc5e-288">如果有一个名为的对应同步操作 `Operation` 返回 `T` ，则应将异步操作命名为（ `AsyncOperation` 如果它返回） `Async<T>` 或返回 `OperationAsync` `Task<T>` 。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-288">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="1fc5e-289">对于公开开始/结束方法的常用 .NET 类型，请考虑使用 `Async.FromBeginEnd` 将扩展方法编写为外观，以便向这些 .Net api 提供 F # 异步编程模型。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-289">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

```fsharp
type SomeType =
    member this.Compute(x:int): int =
        ...
    member this.AsyncCompute(x:int): Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a><span data-ttu-id="1fc5e-290">例外</span><span class="sxs-lookup"><span data-stu-id="1fc5e-290">Exceptions</span></span>

<span data-ttu-id="1fc5e-291">若要了解异常、结果和选项的适当用法，请参阅[错误管理](conventions.md#error-management)。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-291">See [Error Management](conventions.md#error-management) to learn about appropriate use of exceptions, results, and options.</span></span>

### <a name="extension-members"></a><span data-ttu-id="1fc5e-292">扩展成员</span><span class="sxs-lookup"><span data-stu-id="1fc5e-292">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="1fc5e-293">仔细应用 F # 到 F # 组件中的 F # 扩展成员</span><span class="sxs-lookup"><span data-stu-id="1fc5e-293">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="1fc5e-294">F # 扩展成员通常仅适用于在其使用的大多数模式下与类型相关联的内部操作的关闭操作。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-294">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="1fc5e-295">一种常见用途是为各种 .NET 类型提供更惯用 F # 的 Api：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-295">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="1fc5e-296">联合类型</span><span class="sxs-lookup"><span data-stu-id="1fc5e-296">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="1fc5e-297">对树结构数据使用可区分联合，而不是类层次结构</span><span class="sxs-lookup"><span data-stu-id="1fc5e-297">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="1fc5e-298">以递归方式定义类似树的结构。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-298">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="1fc5e-299">这对继承非常难，但在可区分联合的情况下典雅。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-299">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="1fc5e-300">用可区分联合表示类似于树的数据还可让你从模式匹配中的 exhaustiveness 受益。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-300">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="1fc5e-301">`[<RequireQualifiedAccess>]`在大小写名称不够唯一的联合类型上使用</span><span class="sxs-lookup"><span data-stu-id="1fc5e-301">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="1fc5e-302">你可能会发现自己在一个域中，其中相同的名称是不同因素的最佳名称，如可区分联合用例。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-302">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="1fc5e-303">您可以使用 `[<RequireQualifiedAccess>]` 来消除事例名称的歧义，以避免由于隐藏依赖于语句排序而导致的混乱错误 `open`</span><span class="sxs-lookup"><span data-stu-id="1fc5e-303">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="1fc5e-304">如果这些类型的设计可能会演化，隐藏二进制兼容 Api 的可区分联合的表示形式</span><span class="sxs-lookup"><span data-stu-id="1fc5e-304">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="1fc5e-305">联合类型依赖于简洁编程模型的 F # 模式匹配窗体。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-305">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="1fc5e-306">如前文所述，如果这些类型的设计可能会演化，应避免暴露具体的数据表示形式。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-306">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="1fc5e-307">例如，可使用私有或内部声明或使用签名文件隐藏可区分联合的表示形式。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-307">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="1fc5e-308">如果未加上地显示可区分的联合，你可能会发现很难对库进行版本分解，而不会破坏用户代码。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-308">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="1fc5e-309">应考虑公开一个或多个活动模式，以允许对类型值进行模式匹配。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-309">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="1fc5e-310">活动模式提供另一种方法，用于向 F # 使用者提供模式匹配，同时避免直接公开 F # 联合类型。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-310">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="1fc5e-311">内联函数和成员约束</span><span class="sxs-lookup"><span data-stu-id="1fc5e-311">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="1fc5e-312">通过隐含的成员约束和静态解析的泛型类型，使用内联函数定义一般数值算法</span><span class="sxs-lookup"><span data-stu-id="1fc5e-312">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="1fc5e-313">算术成员约束和 F # 比较约束是 F # 编程的标准。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-313">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="1fc5e-314">例如，考虑以下代码：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-314">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="1fc5e-315">此函数的类型如下：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-315">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="1fc5e-316">对于数学库中的公共 API，这是一个合适的函数。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-316">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="1fc5e-317">避免使用成员约束来模拟类型类和类型化类型</span><span class="sxs-lookup"><span data-stu-id="1fc5e-317">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="1fc5e-318">可以使用 F # 成员约束来模拟 "有类型的键入"。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-318">It is possible to simulate "duck typing" using F# member constraints.</span></span> <span data-ttu-id="1fc5e-319">但是，使用此的成员不应在 F #-F # 库设计中使用。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-319">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="1fc5e-320">这是因为基于不熟悉或非标准隐式约束的库设计往往导致用户代码变得不灵活，并与一个特定的框架模式相关联。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-320">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="1fc5e-321">此外，通过这种方式大量使用成员约束可能会导致编译时间非常长。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-321">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="1fc5e-322">运算符定义</span><span class="sxs-lookup"><span data-stu-id="1fc5e-322">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="1fc5e-323">避免定义自定义符号运算符</span><span class="sxs-lookup"><span data-stu-id="1fc5e-323">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="1fc5e-324">在某些情况下，自定义运算符非常重要，在大范围的实现代码内非常有用的符号设备。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-324">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="1fc5e-325">对于库的新用户，命名函数通常更易于使用。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-325">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="1fc5e-326">此外，自定义符号运算符很难记录，用户会发现，由于 IDE 和搜索引擎中存在现有限制，因此更难查找有关运算符的帮助。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-326">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="1fc5e-327">因此，最好将您的功能作为命名函数和成员发布，并且仅当符号权益超出了文档和使用它们的认知成本时，才公开此功能的运算符。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-327">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="1fc5e-328">度量单位</span><span class="sxs-lookup"><span data-stu-id="1fc5e-328">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="1fc5e-329">在 F # 代码中仔细使用度量单位添加的类型安全</span><span class="sxs-lookup"><span data-stu-id="1fc5e-329">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="1fc5e-330">其他 .NET 语言查看时，将清除度量单位的其他键入信息。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-330">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="1fc5e-331">请注意，.NET 组件、工具和反射将显示 "类型"-"san-单位"。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-331">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="1fc5e-332">例如，c # 使用者将看到 `float` 而不是 `float<kg>` 。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-332">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="1fc5e-333">类型缩写</span><span class="sxs-lookup"><span data-stu-id="1fc5e-333">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="1fc5e-334">仔细使用类型缩写来简化 F # 代码</span><span class="sxs-lookup"><span data-stu-id="1fc5e-334">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="1fc5e-335">.NET 组件、工具和反射不会查看类型的缩写名称。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-335">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="1fc5e-336">类型缩写的重要用法还会使域显得更复杂，这可能会使用户感到困惑。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-336">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="1fc5e-337">避免其成员和属性本质上不同于要缩写的类型上可用的公共类型的类型缩写</span><span class="sxs-lookup"><span data-stu-id="1fc5e-337">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="1fc5e-338">在这种情况下，要缩写的类型会显示过多关于所定义的实际类型的表示形式。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-338">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="1fc5e-339">相反，请考虑在类类型或单用例可区分联合中包装缩写（或者，如果性能非常重要，请考虑使用结构类型来包装缩写）。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-339">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="1fc5e-340">例如，将多个地图定义为 F # map 的特殊情况，例如：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-340">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="1fc5e-341">但是，此类型的逻辑点符号运算与映射上的操作不相同–例如，查找运算符映射是合理的。[key] 如果该键不在字典中，则返回空列表，而不是引发异常。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-341">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="1fc5e-342">用于其他 .NET 语言的库的指南</span><span class="sxs-lookup"><span data-stu-id="1fc5e-342">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="1fc5e-343">设计用于其他 .NET 语言的库时，必须遵守[.Net 库设计准则](../../standard/design-guidelines/index.md)。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-343">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="1fc5e-344">在本文档中，这些库标记为 vanilla .NET 库，而不是使用无限制的 F # 的面向 F # 构造的库。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-344">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="1fc5e-345">设计 vanilla .NET 库意味着通过最大程度地减少在公共 API 中使用 F # 特定构造，使熟悉的惯用 Api 与 .NET Framework 的其余部分保持一致。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-345">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="1fc5e-346">以下部分介绍了这些规则。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-346">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="1fc5e-347">命名空间和类型设计（适用于其他 .NET 语言的库）</span><span class="sxs-lookup"><span data-stu-id="1fc5e-347">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="1fc5e-348">将 .NET 命名约定应用于组件的公共 API</span><span class="sxs-lookup"><span data-stu-id="1fc5e-348">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="1fc5e-349">请特别注意缩写名称和 .NET 大小写准则的使用。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-349">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="1fc5e-350">使用命名空间、类型和成员作为组件的主要组织结构</span><span class="sxs-lookup"><span data-stu-id="1fc5e-350">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="1fc5e-351">包含公共功能的所有文件都应以 `namespace` 声明开头，而命名空间中的唯一面向公众的实体应为类型。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-351">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="1fc5e-352">不要使用 F # 模块。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-352">Do not use F# modules.</span></span>

<span data-ttu-id="1fc5e-353">使用非公共模块来保存实现代码、实用工具类型和实用工具函数。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-353">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="1fc5e-354">静态类型应优先于模块，因为它们允许 API 的未来发展使用重载，以及可能不会在 F # 模块内使用的其他 .NET API 设计概念。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-354">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="1fc5e-355">例如，代替以下公共 API：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-355">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="1fc5e-356">改为考虑：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-356">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="1fc5e-357">如果类型的设计不会演化，请使用 vanilla .NET Api 中的 F # 记录类型</span><span class="sxs-lookup"><span data-stu-id="1fc5e-357">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="1fc5e-358">F # 记录类型编译为一个简单的 .NET 类。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-358">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="1fc5e-359">它们适用于 Api 中的一些简单的稳定类型。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-359">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="1fc5e-360">请考虑使用 `[<NoEquality>]` 和 `[<NoComparison>]` 属性来禁止自动生成接口。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-360">Consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="1fc5e-361">还应避免在 vanilla .NET Api 中使用可变记录字段，因为这些字段公开公共字段。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-361">Also avoid using mutable record fields in vanilla .NET APIs as these expose a public field.</span></span> <span data-ttu-id="1fc5e-362">始终考虑某个类是否会为 API 的未来发展提供更灵活的选项。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-362">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="1fc5e-363">例如，以下 F # 代码向 c # 使用者公开公共 API：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-363">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="1fc5e-364">F#：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-364">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing: int
        SecondThing: string }
```

<span data-ttu-id="1fc5e-365">C#：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-365">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="1fc5e-366">隐藏 vanilla .NET Api 中 F # 联合类型的表示形式</span><span class="sxs-lookup"><span data-stu-id="1fc5e-366">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="1fc5e-367">F # 联合类型不常用于组件边界，即使对于 F # 到 F # 编码也是如此。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-367">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="1fc5e-368">在组件和库内部使用时，它们是一种优秀的实现设备。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-368">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="1fc5e-369">设计 vanilla .NET API 时，请考虑使用私有声明或签名文件隐藏联合类型的表示形式。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-369">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="1fc5e-370">你还可以使用成员在内部使用联合表示形式来提供所需的类型。面向网络的 API。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-370">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

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

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="1fc5e-371">使用框架的设计模式设计 GUI 和其他组件</span><span class="sxs-lookup"><span data-stu-id="1fc5e-371">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="1fc5e-372">.NET 中提供了许多不同的框架，如 WinForms、WPF 和 ASP.NET。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-372">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="1fc5e-373">如果要设计在这些框架中使用的组件，则应该使用每个的命名和设计约定。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-373">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="1fc5e-374">例如，对于 WPF 编程，为正在设计的类采用 WPF 设计模式。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-374">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="1fc5e-375">对于用户界面编程中的模型，请使用设计模式，如事件和基于通知的集合（如中所述） <xref:System.Collections.ObjectModel> 。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-375">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="1fc5e-376">对象和成员设计（适用于其他 .NET 语言的库）</span><span class="sxs-lookup"><span data-stu-id="1fc5e-376">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="1fc5e-377">使用 CLIEvent 特性公开 .NET 事件</span><span class="sxs-lookup"><span data-stu-id="1fc5e-377">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="1fc5e-378">构造 `DelegateEvent` 具有特定 .net 委托类型的，该类型采用对象和 `EventArgs` （而不是 `Event` ，默认情况下仅使用 `FSharpHandler` 类型），以便以熟悉的方式将事件发布到其他 .net 语言。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-378">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x: int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-that-return-net-tasks"></a><span data-ttu-id="1fc5e-379">将异步操作作为返回 .NET 任务的方法公开</span><span class="sxs-lookup"><span data-stu-id="1fc5e-379">Expose asynchronous operations as methods that return .NET tasks</span></span>

<span data-ttu-id="1fc5e-380">在 .NET 中使用任务来表示活动的异步计算。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-380">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="1fc5e-381">任务通常比 F # 对象少复合 `Async<T>` ，因为它们表示 "已在执行" 任务，不能以执行并行组合的方式组合在一起，或者隐藏取消信号和其他上下文参数的传播。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-381">Tasks are in general less compositional than F# `Async<T>` objects, since they represent "already executing" tasks and can't be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="1fc5e-382">但尽管如此，返回任务的方法是 .NET 上异步编程的标准表示形式。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-382">However, despite this, methods that return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int): Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="1fc5e-383">经常需要接受显式取消标记：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-383">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x: int): Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="1fc5e-384">使用 .NET 委托类型，而不是 F # 函数类型</span><span class="sxs-lookup"><span data-stu-id="1fc5e-384">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="1fc5e-385">此处的 "F # 函数类型" 表示 "箭头" 类型（如） `int -> int` 。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-385">Here "F# function types" mean "arrow" types like `int -> int`.</span></span>

<span data-ttu-id="1fc5e-386">而不是：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-386">Instead of this:</span></span>

```fsharp
member this.Transform(f: int->int) =
    ...
```

<span data-ttu-id="1fc5e-387">执行此操作：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-387">Do this:</span></span>

```fsharp
member this.Transform(f: Func<int,int>) =
    ...
```

<span data-ttu-id="1fc5e-388">F # 函数类型显示为 `class FSharpFunc<T,U>` 其他 .net 语言，并不适合理解委托类型的语言功能和工具。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-388">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understands delegate types.</span></span> <span data-ttu-id="1fc5e-389">在创作目标为 .NET Framework 3.5 或更高版本的高阶方法时， `System.Func` 和 `System.Action` 委托是正确发布的 api，以使 .net 开发人员能够以低的方式使用这些 api。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-389">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="1fc5e-390">（目标为 .NET Framework 2.0 时，系统定义的委托类型会受到更多的限制; 请考虑使用预定义的委托类型，如 `System.Converter<T,U>` 或定义特定委托类型。）</span><span class="sxs-lookup"><span data-stu-id="1fc5e-390">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="1fc5e-391">另一方面，.NET 委托并不自然用于面向 F # 的库（请参阅有关 F # 的库的下一节）。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-391">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="1fc5e-392">因此，开发 vanilla .NET 库的高阶方法时，一种常见的实现策略是使用 F # 函数类型创作所有实现，然后使用委托作为实际 F # 实现顶部的瘦外观创建公共 API。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-392">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="1fc5e-393">使用 TryGetValue 模式而不是返回 F # 选项值，并首选方法重载以将 F # 选项值作为参数</span><span class="sxs-lookup"><span data-stu-id="1fc5e-393">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="1fc5e-394">使用标准的 .NET 设计方法在 vanilla .NET Api 中更好地实现了 Api 中 F # 选项类型的常用模式。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-394">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="1fc5e-395">请考虑使用 bool 返回类型和 out 参数，而不是返回 F # 选项值，如 "TryGetValue" 模式。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-395">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="1fc5e-396">请考虑使用方法重载或可选参数，而不是将 F # 选项值用作参数。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-396">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal: byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x: int, y: int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x: int) = x

member this.ParamOverload(x: int, y: int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="1fc5e-397">使用 .NET 集合接口类型 IEnumerable \< T \> 和 IDictionary \< 键， \> 参数和返回值的值</span><span class="sxs-lookup"><span data-stu-id="1fc5e-397">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="1fc5e-398">避免使用具体的集合类型，如 .NET 数组 `T[]` 、F # 类型和 `list<T>` `Map<Key,Value>` `Set<T>` .net 具体集合类型 `Dictionary<Key,Value>` （如）。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-398">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="1fc5e-399">.NET 库设计指南对于何时使用各种集合类型（如）有很好的建议 `IEnumerable<T>` 。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-399">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="1fc5e-400">在 `T[]` 某些情况下，某些情况下使用数组（）是性能的。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-400">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="1fc5e-401">请注意 `seq<T>` ，尤其是的 F # 别名 `IEnumerable<T>` ，因此，seq 通常是 VANILLA .net API 的合适类型。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-401">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="1fc5e-402">而不是 F # 列表：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-402">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names: string list) =
    ...
```

<span data-ttu-id="1fc5e-403">使用 F # 序列：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-403">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names: seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="1fc5e-404">使用单元类型作为方法的唯一输入类型来定义零参数方法，或用作唯一的返回类型以定义返回 void 的方法</span><span class="sxs-lookup"><span data-stu-id="1fc5e-404">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="1fc5e-405">避免使用单元类型。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-405">Avoid other uses of the unit type.</span></span> <span data-ttu-id="1fc5e-406">这很好：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-406">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x: int) = ()
```

<span data-ttu-id="1fc5e-407">这是错误的：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-407">This is bad:</span></span>

```fsharp
member this.WrongUnit( x: unit, z: int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="1fc5e-408">在 vanilla .NET API 边界上检查 null 值</span><span class="sxs-lookup"><span data-stu-id="1fc5e-408">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="1fc5e-409">由于不变的设计模式和对 F # 类型使用 null 文本的限制，f # 实现代码的值往往更少。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-409">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="1fc5e-410">其他 .NET 语言通常使用 null 作为值。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-410">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="1fc5e-411">因此，公开 vanilla .NET API 的 F # 代码应检查 API 边界的 null 参数，并防止这些值更深入地流向 F # 实现代码。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-411">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="1fc5e-412">`isNull`可以使用模式的函数或模式匹配 `null` 。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-412">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="1fc5e-413">避免使用元组作为返回值</span><span class="sxs-lookup"><span data-stu-id="1fc5e-413">Avoid using tuples as return values</span></span>

<span data-ttu-id="1fc5e-414">相反，更倾向于返回保存聚合数据的命名类型，或使用 out 参数返回多个值。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-414">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="1fc5e-415">虽然元组和结构元组存在于 .NET 中（包括对结构元组的 c # 语言支持），但它们通常不会为 .NET 开发人员提供理想和预期的 API。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-415">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="1fc5e-416">避免使用参数的 currying</span><span class="sxs-lookup"><span data-stu-id="1fc5e-416">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="1fc5e-417">请改用 .NET 调用约定 `Method(arg1,arg2,…,argN)` 。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-417">Instead, use .NET calling conventions `Method(arg1,arg2,…,argN)`.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="1fc5e-418">提示：如果你正在设计用于任何 .NET 语言的库，则不能使用它来实际执行某些试验性 c # 和 Visual Basic 编程，以确保你的库从这些语言 "感觉正确"。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-418">Tip: If you're designing libraries for use from any .NET language, then there's no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="1fc5e-419">你还可以使用 .NET 反射器和 Visual Studio 对象浏览器等工具来确保库及其文档与开发人员按预期方式显示。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-419">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="1fc5e-420">附录</span><span class="sxs-lookup"><span data-stu-id="1fc5e-420">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="1fc5e-421">设计用于其他 .NET 语言的 F # 代码的端到端示例</span><span class="sxs-lookup"><span data-stu-id="1fc5e-421">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="1fc5e-422">请考虑以下类：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-422">Consider the following class:</span></span>

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

<span data-ttu-id="1fc5e-423">此类的推断 F # 类型如下所示：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-423">The inferred F# type of this class is as follows:</span></span>

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

<span data-ttu-id="1fc5e-424">让我们看一下如何使用另一种 .NET 语言向程序员显示此 F # 类型。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-424">Let's take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="1fc5e-425">例如，"签名" 大致如下所示：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-425">For example, the approximate C# "signature" is as follows:</span></span>

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

<span data-ttu-id="1fc5e-426">有关 F # 表示构造的信息，请注意以下几点。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-426">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="1fc5e-427">例如：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-427">For example:</span></span>

* <span data-ttu-id="1fc5e-428">参数名称等元数据已保留。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-428">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="1fc5e-429">采用两个参数的 F # 方法成为采用两个自变量的 c # 方法。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-429">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="1fc5e-430">函数和列表将成为 F # 库中的相应类型的引用。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-430">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="1fc5e-431">下面的代码演示如何调整此代码以考虑这些问题。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-431">The following code shows how to adjust this code to take these things into account.</span></span>

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

<span data-ttu-id="1fc5e-432">推断出的 F # 类型的代码如下所示：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-432">The inferred F# type of the code is as follows:</span></span>

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

<span data-ttu-id="1fc5e-433">现在，c # 签名如下所示：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-433">The C# signature is now as follows:</span></span>

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

<span data-ttu-id="1fc5e-434">为准备此类型作为 vanilla .NET 库的一部分而进行的修复，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1fc5e-434">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="1fc5e-435">调整了几个名称： `Point1` 、 `n` 、 `l` 和 `f` 分别为 `RadialPoint` 、 `count` `factor` `transform` 、和。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-435">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="1fc5e-436">使用的返回类型， `seq<RadialPoint>` 而不是 `RadialPoint list` 通过将使用的列表构造更改 `[ ... ]` 为使用的序列构造 `IEnumerable<RadialPoint>` 。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-436">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="1fc5e-437">使用 .NET 委托类型， `System.Func` 而不是 F # 函数类型。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-437">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="1fc5e-438">这使得在 c # 代码中使用更好。</span><span class="sxs-lookup"><span data-stu-id="1fc5e-438">This makes it far nicer to consume in C# code.</span></span>
