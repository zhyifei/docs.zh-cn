---
title: F#组件设计准则
description: 了解以进行写入的准则F#面向消费由其他调用方的组件。
ms.date: 05/14/2018
ms.openlocfilehash: bc8d4908912c4630f649ba30593d43a557278efa
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145668"
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="e326b-103">F#组件设计准则</span><span class="sxs-lookup"><span data-stu-id="e326b-103">F# component design guidelines</span></span>

<span data-ttu-id="e326b-104">本文档是一套组件设计准则F#进行编程，基于F#组件设计准则、 v14，Microsoft Research 和[另一个版本](https://fsharp.org/specs/component-design-guidelines/)最初策划和维护的F#软件的基础。</span><span class="sxs-lookup"><span data-stu-id="e326b-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and [another version](https://fsharp.org/specs/component-design-guidelines/) originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="e326b-105">本文档假定您熟悉F#编程。</span><span class="sxs-lookup"><span data-stu-id="e326b-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="e326b-106">多感谢对F#社区的贡献和在本指南的各个版本的有用反馈。</span><span class="sxs-lookup"><span data-stu-id="e326b-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="e326b-107">概述</span><span class="sxs-lookup"><span data-stu-id="e326b-107">Overview</span></span>

<span data-ttu-id="e326b-108">本文档探讨一些与相关的问题F#组件设计和编码。</span><span class="sxs-lookup"><span data-stu-id="e326b-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="e326b-109">组件可能意味着以下任一项：</span><span class="sxs-lookup"><span data-stu-id="e326b-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="e326b-110">中的层在F#项目中具有该项目中的外部使用者。</span><span class="sxs-lookup"><span data-stu-id="e326b-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="e326b-111">适用于使用情况的库F#跨程序集边界的代码。</span><span class="sxs-lookup"><span data-stu-id="e326b-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="e326b-112">跨程序集边界的任何.NET 语言适用于使用一个库。</span><span class="sxs-lookup"><span data-stu-id="e326b-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="e326b-113">一个库，如适用于通过包存储库，将其分发[NuGet](https://nuget.org)。</span><span class="sxs-lookup"><span data-stu-id="e326b-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="e326b-114">请按照本文中所述的技术[良好的五个原则F#代码](index.md#five-principles-of-good-f-code)，因此利用同时功能和对象根据编程。</span><span class="sxs-lookup"><span data-stu-id="e326b-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="e326b-115">方法，无论组件和库设计器时尝试创建一个 API，开发人员可以非常轻松地使用人脸可行且十分普通的问题的数。</span><span class="sxs-lookup"><span data-stu-id="e326b-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="e326b-116">下降的应用程序[.NET 类库设计准则](../../standard/design-guidelines/index.md)将引导你创建一组一致的愉快，若要使用的 Api。</span><span class="sxs-lookup"><span data-stu-id="e326b-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="e326b-117">通用准则</span><span class="sxs-lookup"><span data-stu-id="e326b-117">General guidelines</span></span>

<span data-ttu-id="e326b-118">有几个通用指导原则适用于F#库，而不考虑在库的目标受众。</span><span class="sxs-lookup"><span data-stu-id="e326b-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="e326b-119">了解.NET 类库设计准则</span><span class="sxs-lookup"><span data-stu-id="e326b-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="e326b-120">而不考虑类型的F#编码执行时，它非常有价值有实际的了解[.NET 类库设计准则](../../standard/design-guidelines/index.md)。</span><span class="sxs-lookup"><span data-stu-id="e326b-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="e326b-121">大多数其他F#.NET 编程人员将熟悉这些指导原则，并期望.NET 代码，以符合它们。</span><span class="sxs-lookup"><span data-stu-id="e326b-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="e326b-122">.NET 类库设计准则提供常规指南有关命名、 设计类和接口、 成员 （属性、 方法、 事件等） 的设计和的详细信息，并且引用的各种设计指南的有用的第一个点。</span><span class="sxs-lookup"><span data-stu-id="e326b-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="e326b-123">将 XML 文档注释添加到你的代码</span><span class="sxs-lookup"><span data-stu-id="e326b-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="e326b-124">公共 Api 的 XML 文档，请确保用户可以获得很好的 Intellisense 和快速信息，使用这些类型和成员，以及启用生成文档文件的库时。</span><span class="sxs-lookup"><span data-stu-id="e326b-124">XML documentation on public APIs ensure that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="e326b-125">请参阅[XML 文档](../language-reference/xml-documentation.md)有关各种可用于其他标记内 xmldoc 注释的 xml 标记。</span><span class="sxs-lookup"><span data-stu-id="e326b-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

<span data-ttu-id="e326b-126">您可以使用缩写形式 XML 注释 (`/// comment`)，或标准的 XML 注释 (`///<summary>comment</summary>`)。</span><span class="sxs-lookup"><span data-stu-id="e326b-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="e326b-127">请考虑使用稳定的库和组件 Api 显式签名文件 (.fsi)</span><span class="sxs-lookup"><span data-stu-id="e326b-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="e326b-128">使用显式的签名文件中F#库提供的公共 API，这两者都可帮助确保您知道完整公共图面上的库，也因为提供了公共文档之间完全分离和内部简洁摘要实现详细信息。</span><span class="sxs-lookup"><span data-stu-id="e326b-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which both helps to ensure that you know the full public surface of your library, as well as provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="e326b-129">请注意，签名文件会将冲突添加到更改公共 API，通过要求在实现和签名文件中进行更改。</span><span class="sxs-lookup"><span data-stu-id="e326b-129">Note that signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="e326b-130">因此，签名文件通常只时应引入 API 变得日臻完善和不再需要显著更改。</span><span class="sxs-lookup"><span data-stu-id="e326b-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="e326b-131">在.NET 中使用字符串的最佳实践，应始终遵循</span><span class="sxs-lookup"><span data-stu-id="e326b-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="e326b-132">请按照[在.NET 中使用字符串的最佳做法](../../standard/base-types/best-practices-strings.md)指南。</span><span class="sxs-lookup"><span data-stu-id="e326b-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="e326b-133">具体而言，始终显式声明*区域性意向*中转换和比较字符串 （如果适用）。</span><span class="sxs-lookup"><span data-stu-id="e326b-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="e326b-134">准则F#-面向库</span><span class="sxs-lookup"><span data-stu-id="e326b-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="e326b-135">本部分提供了建议，用于确定公共F#-面向库;即，库公开公共 Api，旨在通过使用F#开发人员。</span><span class="sxs-lookup"><span data-stu-id="e326b-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="e326b-136">有各种库设计建议适用于F#。</span><span class="sxs-lookup"><span data-stu-id="e326b-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="e326b-137">如果没有按照具体建议，.NET 类库设计准则是回退的指南。</span><span class="sxs-lookup"><span data-stu-id="e326b-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="e326b-138">命名约定</span><span class="sxs-lookup"><span data-stu-id="e326b-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="e326b-139">使用.NET 命名和大小写约定</span><span class="sxs-lookup"><span data-stu-id="e326b-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="e326b-140">下表遵循.NET 命名和大小写约定。</span><span class="sxs-lookup"><span data-stu-id="e326b-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="e326b-141">小添加还包括了F#构造。</span><span class="sxs-lookup"><span data-stu-id="e326b-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="e326b-142">构造</span><span class="sxs-lookup"><span data-stu-id="e326b-142">Construct</span></span> | <span data-ttu-id="e326b-143">Case</span><span class="sxs-lookup"><span data-stu-id="e326b-143">Case</span></span> | <span data-ttu-id="e326b-144">部件</span><span class="sxs-lookup"><span data-stu-id="e326b-144">Part</span></span> | <span data-ttu-id="e326b-145">示例</span><span class="sxs-lookup"><span data-stu-id="e326b-145">Examples</span></span> | <span data-ttu-id="e326b-146">说明</span><span class="sxs-lookup"><span data-stu-id="e326b-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="e326b-147">具体的类型</span><span class="sxs-lookup"><span data-stu-id="e326b-147">Concrete types</span></span> | <span data-ttu-id="e326b-148">Pascal 命名法</span><span class="sxs-lookup"><span data-stu-id="e326b-148">PascalCase</span></span> | <span data-ttu-id="e326b-149">名词 / 形容词</span><span class="sxs-lookup"><span data-stu-id="e326b-149">Noun/ adjective</span></span> | <span data-ttu-id="e326b-150">列表中，双精度，复杂</span><span class="sxs-lookup"><span data-stu-id="e326b-150">List, Double, Complex</span></span> | <span data-ttu-id="e326b-151">具体类型是结构、 类、 枚举、 委托、 记录和联合。</span><span class="sxs-lookup"><span data-stu-id="e326b-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="e326b-152">尽管类型名称为 OCaml，在传统上小写F#已采用了.NET 类型的命名方案。</span><span class="sxs-lookup"><span data-stu-id="e326b-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="e326b-153">DLL</span><span class="sxs-lookup"><span data-stu-id="e326b-153">DLLs</span></span>           | <span data-ttu-id="e326b-154">Pascal 命名法</span><span class="sxs-lookup"><span data-stu-id="e326b-154">PascalCase</span></span> |                 | <span data-ttu-id="e326b-155">Fabrikam.Core.dll</span><span class="sxs-lookup"><span data-stu-id="e326b-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="e326b-156">联合标记</span><span class="sxs-lookup"><span data-stu-id="e326b-156">Union tags</span></span>     | <span data-ttu-id="e326b-157">Pascal 命名法</span><span class="sxs-lookup"><span data-stu-id="e326b-157">PascalCase</span></span> | <span data-ttu-id="e326b-158">名词</span><span class="sxs-lookup"><span data-stu-id="e326b-158">Noun</span></span> | <span data-ttu-id="e326b-159">一些，添加成功</span><span class="sxs-lookup"><span data-stu-id="e326b-159">Some, Add, Success</span></span> | <span data-ttu-id="e326b-160">不要在公共 Api 中使用前缀。</span><span class="sxs-lookup"><span data-stu-id="e326b-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="e326b-161">（可选） 使用的前缀时内部的如 \`键入团队 = TAlpha</span><span class="sxs-lookup"><span data-stu-id="e326b-161">Optionally use a prefix when internal, such as \`type Teams = TAlpha</span></span> | <span data-ttu-id="e326b-162">TBeta</span><span class="sxs-lookup"><span data-stu-id="e326b-162">TBeta</span></span> | <span data-ttu-id="e326b-163">TDelta\`</span><span class="sxs-lookup"><span data-stu-id="e326b-163">TDelta.\`</span></span> |
| <span data-ttu-id="e326b-164">事件</span><span class="sxs-lookup"><span data-stu-id="e326b-164">Event</span></span>          | <span data-ttu-id="e326b-165">Pascal 命名法</span><span class="sxs-lookup"><span data-stu-id="e326b-165">PascalCase</span></span> | <span data-ttu-id="e326b-166">谓词</span><span class="sxs-lookup"><span data-stu-id="e326b-166">Verb</span></span> | <span data-ttu-id="e326b-167">ValueChanged / ValueChanging</span><span class="sxs-lookup"><span data-stu-id="e326b-167">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="e326b-168">Exceptions</span><span class="sxs-lookup"><span data-stu-id="e326b-168">Exceptions</span></span>     | <span data-ttu-id="e326b-169">Pascal 命名法</span><span class="sxs-lookup"><span data-stu-id="e326b-169">PascalCase</span></span> |      | <span data-ttu-id="e326b-170">WebException</span><span class="sxs-lookup"><span data-stu-id="e326b-170">WebException</span></span> | <span data-ttu-id="e326b-171">名称应以"Exception"结尾。</span><span class="sxs-lookup"><span data-stu-id="e326b-171">Name should end with “Exception”.</span></span> |
| <span data-ttu-id="e326b-172">字段</span><span class="sxs-lookup"><span data-stu-id="e326b-172">Field</span></span>          | <span data-ttu-id="e326b-173">Pascal 命名法</span><span class="sxs-lookup"><span data-stu-id="e326b-173">PascalCase</span></span> | <span data-ttu-id="e326b-174">名词</span><span class="sxs-lookup"><span data-stu-id="e326b-174">Noun</span></span> | <span data-ttu-id="e326b-175">CurrentName</span><span class="sxs-lookup"><span data-stu-id="e326b-175">CurrentName</span></span>  | |
| <span data-ttu-id="e326b-176">接口类型</span><span class="sxs-lookup"><span data-stu-id="e326b-176">Interface types</span></span> |  <span data-ttu-id="e326b-177">Pascal 命名法</span><span class="sxs-lookup"><span data-stu-id="e326b-177">PascalCase</span></span> | <span data-ttu-id="e326b-178">名词 / 形容词</span><span class="sxs-lookup"><span data-stu-id="e326b-178">Noun/ adjective</span></span> | <span data-ttu-id="e326b-179">IDisposable</span><span class="sxs-lookup"><span data-stu-id="e326b-179">IDisposable</span></span> | <span data-ttu-id="e326b-180">名称应以"I"开头。</span><span class="sxs-lookup"><span data-stu-id="e326b-180">Name should start with “I”.</span></span> |
| <span data-ttu-id="e326b-181">方法</span><span class="sxs-lookup"><span data-stu-id="e326b-181">Method</span></span> |  <span data-ttu-id="e326b-182">Pascal 命名法</span><span class="sxs-lookup"><span data-stu-id="e326b-182">PascalCase</span></span> |  <span data-ttu-id="e326b-183">谓词</span><span class="sxs-lookup"><span data-stu-id="e326b-183">Verb</span></span> | <span data-ttu-id="e326b-184">ToString</span><span class="sxs-lookup"><span data-stu-id="e326b-184">ToString</span></span> | |
| <span data-ttu-id="e326b-185">命名空间</span><span class="sxs-lookup"><span data-stu-id="e326b-185">Namespace</span></span> | <span data-ttu-id="e326b-186">Pascal 命名法</span><span class="sxs-lookup"><span data-stu-id="e326b-186">PascalCase</span></span> | | <span data-ttu-id="e326b-187">Microsoft.FSharp.Core</span><span class="sxs-lookup"><span data-stu-id="e326b-187">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="e326b-188">通常情况下使用`<Organization>.<Technology>[.<Subnamespace>]`，但是如果独立于组织的技术是删除组织。</span><span class="sxs-lookup"><span data-stu-id="e326b-188">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="e326b-189">参数</span><span class="sxs-lookup"><span data-stu-id="e326b-189">Parameters</span></span> | <span data-ttu-id="e326b-190">驼峰式大小写</span><span class="sxs-lookup"><span data-stu-id="e326b-190">camelCase</span></span> | <span data-ttu-id="e326b-191">名词</span><span class="sxs-lookup"><span data-stu-id="e326b-191">Noun</span></span> |  <span data-ttu-id="e326b-192">类型名称、 转换、 范围</span><span class="sxs-lookup"><span data-stu-id="e326b-192">typeName, transform, range</span></span> | |
| <span data-ttu-id="e326b-193">允许值 （内部）</span><span class="sxs-lookup"><span data-stu-id="e326b-193">let values (internal)</span></span> | <span data-ttu-id="e326b-194">驼峰式大小写或 pascal 命名法</span><span class="sxs-lookup"><span data-stu-id="e326b-194">camelCase or PascalCase</span></span> | <span data-ttu-id="e326b-195">名词 / 动词</span><span class="sxs-lookup"><span data-stu-id="e326b-195">Noun/ verb</span></span> |  <span data-ttu-id="e326b-196">getValue myTable</span><span class="sxs-lookup"><span data-stu-id="e326b-196">getValue, myTable</span></span> |
| <span data-ttu-id="e326b-197">允许值 （外部）</span><span class="sxs-lookup"><span data-stu-id="e326b-197">let values (external)</span></span> | <span data-ttu-id="e326b-198">驼峰式大小写或 pascal 命名法</span><span class="sxs-lookup"><span data-stu-id="e326b-198">camelCase or PascalCase</span></span> | <span data-ttu-id="e326b-199">名词/动词</span><span class="sxs-lookup"><span data-stu-id="e326b-199">Noun/verb</span></span>  | <span data-ttu-id="e326b-200">List.map Dates.Today</span><span class="sxs-lookup"><span data-stu-id="e326b-200">List.map, Dates.Today</span></span> | <span data-ttu-id="e326b-201">let 绑定值通常是公共的遵循传统的功能性设计模式时。</span><span class="sxs-lookup"><span data-stu-id="e326b-201">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="e326b-202">但是，通常使用 pascal 命名法标识符可以使用从其他.NET 语言时如此。</span><span class="sxs-lookup"><span data-stu-id="e326b-202">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="e326b-203">属性</span><span class="sxs-lookup"><span data-stu-id="e326b-203">Property</span></span>  | <span data-ttu-id="e326b-204">Pascal 命名法</span><span class="sxs-lookup"><span data-stu-id="e326b-204">PascalCase</span></span>  | <span data-ttu-id="e326b-205">名词 / 形容词</span><span class="sxs-lookup"><span data-stu-id="e326b-205">Noun/ adjective</span></span>  | <span data-ttu-id="e326b-206">IsEndOfFile，背景色</span><span class="sxs-lookup"><span data-stu-id="e326b-206">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="e326b-207">布尔型属性通常使用是的可以并应该是肯定的如 IsEndOfFile，不 IsNotEndOfFile 中所示。</span><span class="sxs-lookup"><span data-stu-id="e326b-207">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="e326b-208">避免缩写</span><span class="sxs-lookup"><span data-stu-id="e326b-208">Avoid abbreviations</span></span>

<span data-ttu-id="e326b-209">.NET 指南不鼓励使用缩写的使用 (例如，"使用`OnButtonClick`而非`OnBtnClick`")。</span><span class="sxs-lookup"><span data-stu-id="e326b-209">The .NET guidelines discourage the use of abbreviations (for example, “use `OnButtonClick` rather than `OnBtnClick`”).</span></span> <span data-ttu-id="e326b-210">常见的缩写词，如`Async`允许为"异步"。</span><span class="sxs-lookup"><span data-stu-id="e326b-210">Common abbreviations, such as `Async` for “Asynchronous”, are tolerated.</span></span> <span data-ttu-id="e326b-211">对函数式编程; 有时还会忽略此准则例如，`List.iter`用于一个缩写词"迭代"。</span><span class="sxs-lookup"><span data-stu-id="e326b-211">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for “iterate”.</span></span> <span data-ttu-id="e326b-212">出于此原因，使用缩写通常在更大程度上是可以容忍F#到F#进行编程，但仍通常应避免在公共组件设计。</span><span class="sxs-lookup"><span data-stu-id="e326b-212">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="e326b-213">避免名称冲突的大小写</span><span class="sxs-lookup"><span data-stu-id="e326b-213">Avoid casing name collisions</span></span>

<span data-ttu-id="e326b-214">.NET 指南中指出，单独的大小写不能用于消除名称冲突，因为某些客户端语言 (例如，Visual Basic 中) 都不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="e326b-214">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="e326b-215">在适用处使用首字母缩写词</span><span class="sxs-lookup"><span data-stu-id="e326b-215">Use acronyms where appropriate</span></span>

<span data-ttu-id="e326b-216">首字母缩写词，如 XML 不缩写和首字母未大写形式 (Xml) 的.NET 库中广泛使用。</span><span class="sxs-lookup"><span data-stu-id="e326b-216">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="e326b-217">仅应使用的已知的普遍公认首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="e326b-217">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="e326b-218">为泛型参数名称使用 pascal 命名法</span><span class="sxs-lookup"><span data-stu-id="e326b-218">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="e326b-219">使用 pascal 命名法为公共 Api，包括适用于中的泛型参数名称F#-面向库。</span><span class="sxs-lookup"><span data-stu-id="e326b-219">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="e326b-220">具体而言，使用类似的名称`T`， `U`， `T1`，`T2`任意泛型参数，和特定名称很有用，然后F#的面向公众的库使用类似名称`Key`， `Value`，`Arg` (但不是能， `TKey`)。</span><span class="sxs-lookup"><span data-stu-id="e326b-220">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="e326b-221">为公共函数和中的值使用 pascal 命名法或驼峰式大小写F#模块</span><span class="sxs-lookup"><span data-stu-id="e326b-221">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="e326b-222">对于设计用于的公共函数使用驼峰式大小写不合格 (例如， `invalidArg`)，以及"标准集合函数"（例如，List.map）。</span><span class="sxs-lookup"><span data-stu-id="e326b-222">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the “standard collection functions” (for example, List.map).</span></span> <span data-ttu-id="e326b-223">在这两个这些情况下，函数名称作用类似语言中的关键字。</span><span class="sxs-lookup"><span data-stu-id="e326b-223">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="e326b-224">对象、 类型和模块的设计</span><span class="sxs-lookup"><span data-stu-id="e326b-224">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="e326b-225">使用命名空间或模块包含类型和模块</span><span class="sxs-lookup"><span data-stu-id="e326b-225">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="e326b-226">每个F#组件中的文件应以命名空间声明或模块声明开头。</span><span class="sxs-lookup"><span data-stu-id="e326b-226">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="e326b-227">或</span><span class="sxs-lookup"><span data-stu-id="e326b-227">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="e326b-228">使用模块和命名空间来组织代码最高级别之间的区别是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e326b-228">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="e326b-229">命名空间可以跨多个文件</span><span class="sxs-lookup"><span data-stu-id="e326b-229">Namespaces can span multiple files</span></span>
* <span data-ttu-id="e326b-230">命名空间不能包含F#函数，除非它们是内部模块内</span><span class="sxs-lookup"><span data-stu-id="e326b-230">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="e326b-231">为任何给定模块的代码必须包含在单个文件</span><span class="sxs-lookup"><span data-stu-id="e326b-231">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="e326b-232">顶级模块可以包含F#函数而无需内部模块</span><span class="sxs-lookup"><span data-stu-id="e326b-232">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="e326b-233">顶级命名空间或模块之间的选择会影响代码的已编译的形式，因此会影响将视图从其他.NET 语言应 API 最终使用外部的F#代码。</span><span class="sxs-lookup"><span data-stu-id="e326b-233">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="e326b-234">使用方法和属性的对象类型中的内部操作</span><span class="sxs-lookup"><span data-stu-id="e326b-234">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="e326b-235">当使用对象，最好以确保可使用的功能作为方法和对该类型的属性。</span><span class="sxs-lookup"><span data-stu-id="e326b-235">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="e326b-236">给定成员的大容量的功能需要不一定在中实现该成员，但应为可使用项的功能。</span><span class="sxs-lookup"><span data-stu-id="e326b-236">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="e326b-237">使用类来封装的可变状态</span><span class="sxs-lookup"><span data-stu-id="e326b-237">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="e326b-238">在F#，这只需要完成的状态未已封装由另一个语言构造，如闭包、 序列表达式或异步计算。</span><span class="sxs-lookup"><span data-stu-id="e326b-238">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="e326b-239">使用接口来分组相关的操作</span><span class="sxs-lookup"><span data-stu-id="e326b-239">Use interfaces to group related operations</span></span>

<span data-ttu-id="e326b-240">使用接口类型来表示一组操作。</span><span class="sxs-lookup"><span data-stu-id="e326b-240">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="e326b-241">这是优先于其他选项，例如元组的函数或函数的记录。</span><span class="sxs-lookup"><span data-stu-id="e326b-241">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="e326b-242">在优先于：</span><span class="sxs-lookup"><span data-stu-id="e326b-242">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

<span data-ttu-id="e326b-243">接口是在.NET 中，这可用于实现什么函子将通常为您提供的第一级概念。</span><span class="sxs-lookup"><span data-stu-id="e326b-243">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="e326b-244">此外，它们可以用于编码为您的程序，记录的函数不能存在的类型。</span><span class="sxs-lookup"><span data-stu-id="e326b-244">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a><span data-ttu-id="e326b-245">在集合上使用组函数执行操作的模块</span><span class="sxs-lookup"><span data-stu-id="e326b-245">Use a module to group functions which act on collections</span></span>

<span data-ttu-id="e326b-246">在定义集合类型时，请考虑提供一组标准的操作等`CollectionType.map`和`CollectionType.iter`) 的新集合类型。</span><span class="sxs-lookup"><span data-stu-id="e326b-246">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="e326b-247">如果包含此类模块，请按照找到 FSharp.Core 中的函数的标准命名约定。</span><span class="sxs-lookup"><span data-stu-id="e326b-247">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="e326b-248">对于常见的规范函数，特别是在数学和 DSL 库使用的模块组函数</span><span class="sxs-lookup"><span data-stu-id="e326b-248">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="e326b-249">例如，`Microsoft.FSharp.Core.Operators`是一个自动打开顶层函数的集合 (如`abs`和`sin`) 提供的 FSharp.Core.dll。</span><span class="sxs-lookup"><span data-stu-id="e326b-249">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="e326b-250">同样，一个库，统计信息可能包括具有函数的模块`erf`和`erfc`，而此模块用于显式或自动打开。</span><span class="sxs-lookup"><span data-stu-id="e326b-250">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="e326b-251">请考虑使用 RequireQualifiedAccess 并仔细应用 AutoOpen 特性</span><span class="sxs-lookup"><span data-stu-id="e326b-251">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="e326b-252">添加`[<RequireQualifiedAccess>]`对模块的特性指示模块不能打开，并且对模块的元素的引用需要显式限定访问权限。</span><span class="sxs-lookup"><span data-stu-id="e326b-252">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="e326b-253">例如，`Microsoft.FSharp.Collections.List`模块具有此属性。</span><span class="sxs-lookup"><span data-stu-id="e326b-253">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="e326b-254">当函数和模块中的值具有名称可能与其他模块中的名称发生冲突时，这很有用。</span><span class="sxs-lookup"><span data-stu-id="e326b-254">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="e326b-255">需要限定的访问可以极大地提高的长期可维护性和可进化性的库。</span><span class="sxs-lookup"><span data-stu-id="e326b-255">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="e326b-256">添加`[<AutoOpen>]`对模块的属性就意味着，打开包含的命名空间时将打开该模块。</span><span class="sxs-lookup"><span data-stu-id="e326b-256">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="e326b-257">`[<AutoOpen>]`还可以将特性应用于程序集可指示模块引用的程序集时自动打开。</span><span class="sxs-lookup"><span data-stu-id="e326b-257">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="e326b-258">例如，统计信息库**MathsHeaven.Statistics**可能包含`module MathsHeaven.Statistics.Operators`包含函数`erf`和`erfc`。</span><span class="sxs-lookup"><span data-stu-id="e326b-258">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="e326b-259">它是合理地将标记为此模块`[<AutoOpen>]`。</span><span class="sxs-lookup"><span data-stu-id="e326b-259">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="e326b-260">这意味着`open MathsHeaven.Statistics`还将打开此模块并将名称`erf`和`erfc`纳入范围。</span><span class="sxs-lookup"><span data-stu-id="e326b-260">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="e326b-261">使用另一个良好`[<AutoOpen>]`是包含扩展方法的模块。</span><span class="sxs-lookup"><span data-stu-id="e326b-261">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="e326b-262">使用过度的`[<AutoOpen>]`导致受到污染命名空间和该属性应谨慎使用。</span><span class="sxs-lookup"><span data-stu-id="e326b-262">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="e326b-263">特定库中特定域，明智地使用`[<AutoOpen>]`可能会导致更好的可用性。</span><span class="sxs-lookup"><span data-stu-id="e326b-263">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="e326b-264">请考虑在其中使用众所周知的运算符是适当的类上定义运算符成员</span><span class="sxs-lookup"><span data-stu-id="e326b-264">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="e326b-265">有时类用于建模数学构造，例如向量。</span><span class="sxs-lookup"><span data-stu-id="e326b-265">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="e326b-266">当要建模的域具有众所周知的运算符时，将其定义为类中的内部成员非常有用。</span><span class="sxs-lookup"><span data-stu-id="e326b-266">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="e326b-267">本指南对应于这些类型的常规.NET 指南。</span><span class="sxs-lookup"><span data-stu-id="e326b-267">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="e326b-268">但是，它可以是在非常重要F#编写代码，因为这会使这些类型结合使用F#函数和成员约束，例如 List.sumBy 使用的方法。</span><span class="sxs-lookup"><span data-stu-id="e326b-268">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="e326b-269">请考虑使用 CompiledName 来提供。其他.NET 语言的使用者的 NET 的友好名称</span><span class="sxs-lookup"><span data-stu-id="e326b-269">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="e326b-270">有时你可能想要提供的名称是中一种样式的F#使用者 (例如，以使其显示的小写形式是静态成员，就好像模块绑定函数)，但编译为程序集时具有不同的样式的名称。</span><span class="sxs-lookup"><span data-stu-id="e326b-270">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="e326b-271">可以使用`[<CompiledName>]`属性来提供不同的样式为非F#使用程序集代码。</span><span class="sxs-lookup"><span data-stu-id="e326b-271">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="e326b-272">通过使用`[<CompiledName>]`，可以使用适用的.NET 命名约定非F#的程序集的使用者。</span><span class="sxs-lookup"><span data-stu-id="e326b-272">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="e326b-273">如果这样做将提供更简单的 API，使用方法重载的成员函数</span><span class="sxs-lookup"><span data-stu-id="e326b-273">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="e326b-274">方法重载是功能强大的工具，用于简化一个 API，可能需要执行类似的功能，但具有不同的选项或参数。</span><span class="sxs-lookup"><span data-stu-id="e326b-274">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="e326b-275">在F#，它是更常见的是重载的参数数目而不是参数的类型。</span><span class="sxs-lookup"><span data-stu-id="e326b-275">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="e326b-276">这些类型的设计是可能会不断变化的情况下隐藏的记录和联合类型的表示形式</span><span class="sxs-lookup"><span data-stu-id="e326b-276">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="e326b-277">避免泄露具体对象的表示形式。</span><span class="sxs-lookup"><span data-stu-id="e326b-277">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="e326b-278">例如，具体的表现形式的<xref:System.DateTime>值不会显示由外部的公共 API 的.NET 库设计。</span><span class="sxs-lookup"><span data-stu-id="e326b-278">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="e326b-279">在运行时，公共语言运行时知道将在整个执行过程中使用的提交的实现。</span><span class="sxs-lookup"><span data-stu-id="e326b-279">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="e326b-280">但是，已编译的代码不本身选取上具体的表现形式的依赖项。</span><span class="sxs-lookup"><span data-stu-id="e326b-280">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="e326b-281">避免使用实现继承的可扩展性</span><span class="sxs-lookup"><span data-stu-id="e326b-281">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="e326b-282">在F#，很少使用实现继承。</span><span class="sxs-lookup"><span data-stu-id="e326b-282">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="e326b-283">此外，继承层次结构通常是将复杂且难以实现，若要更改新的要求到达时。</span><span class="sxs-lookup"><span data-stu-id="e326b-283">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="e326b-284">继承实现仍存在于F#兼容性和极少数情况下，它是最佳解决方案到问题，但应中寻找其他方法在F#程序的多态性，如接口设计时实现。</span><span class="sxs-lookup"><span data-stu-id="e326b-284">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="e326b-285">函数和成员签名</span><span class="sxs-lookup"><span data-stu-id="e326b-285">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="e326b-286">返回值返回少量的多个不相关的值时使用元组</span><span class="sxs-lookup"><span data-stu-id="e326b-286">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="e326b-287">下面是在返回类型中使用元组的一个很好示例：</span><span class="sxs-lookup"><span data-stu-id="e326b-287">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="e326b-288">对于返回类型包含许多组件，或如果单个身份实体与相关组件，应考虑使用命名的类型而不元组。</span><span class="sxs-lookup"><span data-stu-id="e326b-288">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="e326b-289">使用`Async<T>`的异步编程在F#API 边界</span><span class="sxs-lookup"><span data-stu-id="e326b-289">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="e326b-290">如果没有名为相应的同步操作`Operation`，它返回`T`，则应命名为异步操作`AsyncOperation`如果它返回`Async<T>`或`OperationAsync`如果它返回`Task<T>`。</span><span class="sxs-lookup"><span data-stu-id="e326b-290">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="e326b-291">对于常用的.NET 类型公开 Begin/End 方法，请考虑使用`Async.FromBeginEnd`将扩展方法提供的外观为F#的.NET Api 到异步编程模型。</span><span class="sxs-lookup"><span data-stu-id="e326b-291">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

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

### <a name="exceptions"></a><span data-ttu-id="e326b-292">Exceptions</span><span class="sxs-lookup"><span data-stu-id="e326b-292">Exceptions</span></span>

<span data-ttu-id="e326b-293">请参阅[错误管理](conventions.md#error-management)若要了解如何正确使用的异常、 结果和选项。</span><span class="sxs-lookup"><span data-stu-id="e326b-293">See [Error Management](conventions.md#error-management) to learn about appropriate use of exceptions, results, and options.</span></span>

### <a name="extension-members"></a><span data-ttu-id="e326b-294">扩展成员</span><span class="sxs-lookup"><span data-stu-id="e326b-294">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="e326b-295">小心地将应用F#中的扩展成员F#到F#组件</span><span class="sxs-lookup"><span data-stu-id="e326b-295">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="e326b-296">F#扩展成员通常只应与在其模式使用大多数类型关联的内部操作的闭包中的操作。</span><span class="sxs-lookup"><span data-stu-id="e326b-296">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="e326b-297">一种常见用途是提供到更惯用的 ApiF#的各种.NET 类型：</span><span class="sxs-lookup"><span data-stu-id="e326b-297">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="e326b-298">联合类型</span><span class="sxs-lookup"><span data-stu-id="e326b-298">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="e326b-299">而不是类层次结构的可区分的联合用于树结构化数据</span><span class="sxs-lookup"><span data-stu-id="e326b-299">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="e326b-300">类似于树的结构是以递归方式定义。</span><span class="sxs-lookup"><span data-stu-id="e326b-300">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="e326b-301">这是包含继承、 困难但简洁的可区分联合。</span><span class="sxs-lookup"><span data-stu-id="e326b-301">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="e326b-302">表示可区分联合使用类似于树中的数据还使你可以从 exhaustiveness 在模式匹配中受益。</span><span class="sxs-lookup"><span data-stu-id="e326b-302">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="e326b-303">使用`[<RequireQualifiedAccess>]`上其大小写的名称不是足够唯一的联合类型</span><span class="sxs-lookup"><span data-stu-id="e326b-303">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="e326b-304">您可能发现自己在其中相同的名称是用于执行不同操作，例如可区分联合用例的最佳名称的域中。</span><span class="sxs-lookup"><span data-stu-id="e326b-304">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="e326b-305">可以使用`[<RequireQualifiedAccess>]`区分大小写的名称以避免触发由于隐藏依赖于的排序的混淆错误`open`语句</span><span class="sxs-lookup"><span data-stu-id="e326b-305">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="e326b-306">这些类型的设计是可能会不断变化的情况下隐藏二进制兼容的 Api 可区分联合的表示形式</span><span class="sxs-lookup"><span data-stu-id="e326b-306">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="e326b-307">联合类型依赖于F#模式匹配的简洁的编程模型的窗体。</span><span class="sxs-lookup"><span data-stu-id="e326b-307">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="e326b-308">正如前面提到的应避免泄露具体数据表示形式，如果这些类型的设计是可能会不断变化。</span><span class="sxs-lookup"><span data-stu-id="e326b-308">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="e326b-309">例如，可区分联合的表示形式可以隐藏使用私有或内部声明，或通过使用签名文件。</span><span class="sxs-lookup"><span data-stu-id="e326b-309">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="e326b-310">如果不加选择地显示可区分的联合，你可能会发现它很难版本库而不会中断用户代码。</span><span class="sxs-lookup"><span data-stu-id="e326b-310">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="e326b-311">相反，应考虑显示一个或多个活动的模式，以允许针对您的类型的值的模式匹配。</span><span class="sxs-lookup"><span data-stu-id="e326b-311">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="e326b-312">活动模式提供另一种方法提供F#使用者与模式匹配时避免公开F#直接联合类型。</span><span class="sxs-lookup"><span data-stu-id="e326b-312">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="e326b-313">内联函数和成员约束</span><span class="sxs-lookup"><span data-stu-id="e326b-313">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="e326b-314">定义泛型数值算法中使用内联函数的隐式的成员约束和静态解析的泛型类型</span><span class="sxs-lookup"><span data-stu-id="e326b-314">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="e326b-315">算术成员约束和F#比较约束是一种标准F#编程。</span><span class="sxs-lookup"><span data-stu-id="e326b-315">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="e326b-316">例如，考虑以下代码：</span><span class="sxs-lookup"><span data-stu-id="e326b-316">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="e326b-317">此函数的类型是按如下所示：</span><span class="sxs-lookup"><span data-stu-id="e326b-317">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="e326b-318">这是合适的函数的数学库中的公共 API。</span><span class="sxs-lookup"><span data-stu-id="e326b-318">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="e326b-319">避免使用成员约束来模拟类型的类和鸭子类型化</span><span class="sxs-lookup"><span data-stu-id="e326b-319">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="e326b-320">可以模拟"鸭子类型化"使用F#成员约束。</span><span class="sxs-lookup"><span data-stu-id="e326b-320">It is possible to simulate “duck typing” using F# member constraints.</span></span> <span data-ttu-id="e326b-321">但是，成员，从而使利用这一点应在中使用不在常规F#到F#库的设计。</span><span class="sxs-lookup"><span data-stu-id="e326b-321">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="e326b-322">这是因为基于不熟悉或非标准的隐式约束的库设计可能会导致用户代码会变得不灵活且绑定到一个特定的框架模式。</span><span class="sxs-lookup"><span data-stu-id="e326b-322">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="e326b-323">此外，还有很可能会大量使用这种方式中的成员约束可能会很长的编译时间。</span><span class="sxs-lookup"><span data-stu-id="e326b-323">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="e326b-324">运算符定义</span><span class="sxs-lookup"><span data-stu-id="e326b-324">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="e326b-325">避免定义自定义的符号运算符</span><span class="sxs-lookup"><span data-stu-id="e326b-325">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="e326b-326">自定义运算符至关重要，在某些情况下，大量的实现代码中非常有用符号设备。</span><span class="sxs-lookup"><span data-stu-id="e326b-326">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="e326b-327">对于库的新用户，命名的函数通常是易于使用。</span><span class="sxs-lookup"><span data-stu-id="e326b-327">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="e326b-328">此外，自定义的符号运算符可能很难到文档中，并且用户找到更难以查找运算符，由于 IDE 和搜索引擎中的现有限制的帮助。</span><span class="sxs-lookup"><span data-stu-id="e326b-328">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="e326b-329">因此，最好发布您的功能作为命名的函数和成员，并仅当符号好处超过的文档和认知成本经历此外公开此功能的运算符。</span><span class="sxs-lookup"><span data-stu-id="e326b-329">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="e326b-330">度量单位</span><span class="sxs-lookup"><span data-stu-id="e326b-330">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="e326b-331">小心地使用的度量值的单位来实现中添加的类型安全F#代码</span><span class="sxs-lookup"><span data-stu-id="e326b-331">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="e326b-332">其他.NET 语言在查看时，将清除其他单元的度量值的类型化信息。</span><span class="sxs-lookup"><span data-stu-id="e326b-332">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="e326b-333">请注意，.NET 组件、 工具和反射将看到 san 单位类型。</span><span class="sxs-lookup"><span data-stu-id="e326b-333">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="e326b-334">例如，C# 使用者将看到`float`而非`float<kg>`。</span><span class="sxs-lookup"><span data-stu-id="e326b-334">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="e326b-335">类型缩写</span><span class="sxs-lookup"><span data-stu-id="e326b-335">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="e326b-336">小心地使用类型缩写来简化F#代码</span><span class="sxs-lookup"><span data-stu-id="e326b-336">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="e326b-337">.NET 组件、 工具和反射不会看到类型的缩写的名称。</span><span class="sxs-lookup"><span data-stu-id="e326b-337">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="e326b-338">类型缩写的重要使用情况还可以显示比它变得更加复杂实际上是，这可以给消费者带来困惑的域。</span><span class="sxs-lookup"><span data-stu-id="e326b-338">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="e326b-339">避免其成员和属性应为本质上不同可用正在缩写的类型的公共类型的类型缩写</span><span class="sxs-lookup"><span data-stu-id="e326b-339">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="e326b-340">在这种情况下，被缩写的类型将显示有关正在定义的实际类型的表示形式的过多信息。</span><span class="sxs-lookup"><span data-stu-id="e326b-340">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="e326b-341">相反，包装类类型或单用例可区分的联合中的缩写，请考虑 （或基本性能时，请考虑使用结构类型来包装缩写）。</span><span class="sxs-lookup"><span data-stu-id="e326b-341">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="e326b-342">例如，很容易定义多重映射为一种特殊情况的F#映射，例如：</span><span class="sxs-lookup"><span data-stu-id="e326b-342">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="e326b-343">但是，此类型上的逻辑点表示法操作不是在地图上的操作相同 – 例如，它是合理 lookup 运算符映射。[key] 返回空列表如果该键不在字典中，而不引发异常。</span><span class="sxs-lookup"><span data-stu-id="e326b-343">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="e326b-344">用于从其他.NET 语言中使用的库的指导原则</span><span class="sxs-lookup"><span data-stu-id="e326b-344">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="e326b-345">在设计时从其他.NET 语言中使用的库，它是必须遵守[.NET 类库设计准则](../../standard/design-guidelines/index.md)。</span><span class="sxs-lookup"><span data-stu-id="e326b-345">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="e326b-346">在本文档中，这些库标记为普通的.NET 库，而不是F#-面向使用的库F#不受限制地构造。</span><span class="sxs-lookup"><span data-stu-id="e326b-346">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="e326b-347">设计普通的.NET 库意味着提供大家所熟悉且惯用 Api 与.NET Framework 的其余部分保持一致的最大程度减少使用F#-在公共 API 中的特定构造。</span><span class="sxs-lookup"><span data-stu-id="e326b-347">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="e326b-348">以下各节中介绍了这些规则。</span><span class="sxs-lookup"><span data-stu-id="e326b-348">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="e326b-349">Namespace 和类型设计 （适用于从其他.NET 语言中使用的库）</span><span class="sxs-lookup"><span data-stu-id="e326b-349">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="e326b-350">适用于您的组件的公共 API 的.NET 命名约定</span><span class="sxs-lookup"><span data-stu-id="e326b-350">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="e326b-351">应特别注意的缩写的名称和.NET 的大小写准则的使用。</span><span class="sxs-lookup"><span data-stu-id="e326b-351">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="e326b-352">使用命名空间、 类型和成员作为您的组件的主要组织结构</span><span class="sxs-lookup"><span data-stu-id="e326b-352">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="e326b-353">包含公共功能的所有文件应都以开头`namespace`声明，以及命名空间中唯一的面向公众的实体应为类型。</span><span class="sxs-lookup"><span data-stu-id="e326b-353">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="e326b-354">不要使用F#模块。</span><span class="sxs-lookup"><span data-stu-id="e326b-354">Do not use F# modules.</span></span>

<span data-ttu-id="e326b-355">使用非公共模块用于保存实现代码、 实用程序类型和实用工具函数。</span><span class="sxs-lookup"><span data-stu-id="e326b-355">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="e326b-356">静态类型应当优先于模块，因为它们支持的 API 的未来发展使用重载和其他不能使用中的.NET API 设计概念F#模块。</span><span class="sxs-lookup"><span data-stu-id="e326b-356">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="e326b-357">例如，替代以下公共 API:</span><span class="sxs-lookup"><span data-stu-id="e326b-357">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="e326b-358">请考虑改为：</span><span class="sxs-lookup"><span data-stu-id="e326b-358">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="e326b-359">使用F#类型的设计不会演变中传统的.NET Api 记录类型</span><span class="sxs-lookup"><span data-stu-id="e326b-359">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="e326b-360">F#记录类型编译为一个简单的.NET 类。</span><span class="sxs-lookup"><span data-stu-id="e326b-360">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="e326b-361">这些是适用于 Api 中的一些简单的稳定类型。</span><span class="sxs-lookup"><span data-stu-id="e326b-361">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="e326b-362">应考虑使用`[<NoEquality>]`和`[<NoComparison>]`特性禁止显示自动生成的接口。</span><span class="sxs-lookup"><span data-stu-id="e326b-362">You should consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="e326b-363">此外还应避免使用传统的.NET Api 中的可变记录字段作为这些公开一个公共字段。</span><span class="sxs-lookup"><span data-stu-id="e326b-363">Also avoid using mutable record fields in vanilla .NET APIs as these exposes a public field.</span></span> <span data-ttu-id="e326b-364">应始终考虑到一个类是否将提供更灵活的 api 选项未来的发展。</span><span class="sxs-lookup"><span data-stu-id="e326b-364">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="e326b-365">例如，以下F#代码会公开公共 APIC#使用者：</span><span class="sxs-lookup"><span data-stu-id="e326b-365">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="e326b-366">F#:</span><span class="sxs-lookup"><span data-stu-id="e326b-366">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing : int
        SecondThing : string }
```

<span data-ttu-id="e326b-367">C#：</span><span class="sxs-lookup"><span data-stu-id="e326b-367">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="e326b-368">隐藏的表示形式F#在传统的.NET Api 中的联合类型</span><span class="sxs-lookup"><span data-stu-id="e326b-368">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="e326b-369">F#联合类型不常用跨组件边界，即使对于F#到F#编码。</span><span class="sxs-lookup"><span data-stu-id="e326b-369">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="e326b-370">它们是一个极好实现设备时在组件和库内部使用。</span><span class="sxs-lookup"><span data-stu-id="e326b-370">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="e326b-371">在设计时传统的.NET API，请考虑使用专用的声明或签名文件中隐藏的联合类型的表示形式。</span><span class="sxs-lookup"><span data-stu-id="e326b-371">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="e326b-372">您可能会通过扩充联合的表示形式在内部使用与成员提供所需的类型。面向 NET 的 API。</span><span class="sxs-lookup"><span data-stu-id="e326b-372">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

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

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="e326b-373">设计 GUI 和其他组件使用的 framework 的设计模式</span><span class="sxs-lookup"><span data-stu-id="e326b-373">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="e326b-374">在.NET 中，如 WinForms、 WPF 和 ASP.NET 提供了很多不同框架。</span><span class="sxs-lookup"><span data-stu-id="e326b-374">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="e326b-375">如果您正在设计用于在这些框架中使用的组件，应使用为每个命名和设计的约定。</span><span class="sxs-lookup"><span data-stu-id="e326b-375">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="e326b-376">例如，对于 WPF 编程中，采用设计的类的 WPF 设计的模式。</span><span class="sxs-lookup"><span data-stu-id="e326b-376">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="e326b-377">对于在用户界面编程模型，使用设计模式，例如事件，例如那些基于通知的集合中找到<xref:System.Collections.ObjectModel>。</span><span class="sxs-lookup"><span data-stu-id="e326b-377">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="e326b-378">对象和成员设计 （适用于从其他.NET 语言中使用的库）</span><span class="sxs-lookup"><span data-stu-id="e326b-378">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="e326b-379">使用 CLIEvent 特性来公开.NET 事件</span><span class="sxs-lookup"><span data-stu-id="e326b-379">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="e326b-380">构造`DelegateEvent`与特定的.NET 委托采用对象的类型和`EventArgs`(而非`Event`，它只需使用`FSharpHandler`类型默认情况下)，以便事件要发布的方式与其他.NET 语言熟悉。</span><span class="sxs-lookup"><span data-stu-id="e326b-380">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

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

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a><span data-ttu-id="e326b-381">将异步操作公开为方法返回.NET 任务</span><span class="sxs-lookup"><span data-stu-id="e326b-381">Expose asynchronous operations as methods which return .NET tasks</span></span>

<span data-ttu-id="e326b-382">在.NET 中使用任务来表示活动的异步计算。</span><span class="sxs-lookup"><span data-stu-id="e326b-382">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="e326b-383">任务通常比不太组合是F#`Async<T>`对象，因为它们表示"已在执行"任务，不能为组合在一起以执行并行组合，或其隐藏的取消信号传播的方式和其他上下文参数。</span><span class="sxs-lookup"><span data-stu-id="e326b-383">Tasks are in general less compositional than F# `Async<T>` objects, since they represent “already executing” tasks and can’t be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="e326b-384">但是，尽管如此，返回任务的方法是在.NET 异步编程的标准表示形式。</span><span class="sxs-lookup"><span data-stu-id="e326b-384">However, despite this, methods which return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="e326b-385">经常将还想要接受显式取消标记：</span><span class="sxs-lookup"><span data-stu-id="e326b-385">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="e326b-386">使用.NET 委托类型，而不是F#函数类型</span><span class="sxs-lookup"><span data-stu-id="e326b-386">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="e326b-387">此处"F#函数类型"表示"箭头"类型喜欢`int -> int`。</span><span class="sxs-lookup"><span data-stu-id="e326b-387">Here “F# function types” mean “arrow” types like `int -> int`.</span></span>

<span data-ttu-id="e326b-388">而不是以下内容：</span><span class="sxs-lookup"><span data-stu-id="e326b-388">Instead of this:</span></span>

```fsharp
member this.Transform(f:int->int) =
    ...
```

<span data-ttu-id="e326b-389">执行此操作：</span><span class="sxs-lookup"><span data-stu-id="e326b-389">Do this:</span></span>

```fsharp
member this.Transform(f:Func<int,int>) =
    ...
```

<span data-ttu-id="e326b-390">F#函数类型显示为`class FSharpFunc<T,U>`与其他.NET 语言，并不太适用于了解委托类型的语言功能和工具。</span><span class="sxs-lookup"><span data-stu-id="e326b-390">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understand delegate types.</span></span> <span data-ttu-id="e326b-391">创建面向.NET Framework 3.5 或更高版本，一个更高序位方法时`System.Func`和`System.Action`委托是正确的 Api 来发布使.NET 开发人员能够以低冲突的方式使用这些 Api。</span><span class="sxs-lookup"><span data-stu-id="e326b-391">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="e326b-392">(时定目标到.NET Framework 2.0，会限制更多系统定义的委托类型; 请考虑使用预定义的委托类型，如`System.Converter<T,U>`或定义特定委托类型。)</span><span class="sxs-lookup"><span data-stu-id="e326b-392">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="e326b-393">另一方面，.NET 委托不是很自然F#-面向库 (请参阅下一步部分F#-面向库)。</span><span class="sxs-lookup"><span data-stu-id="e326b-393">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="e326b-394">因此，常见的实现策略开发普通的.NET 库的更高序位方法时是创作所有实施方案，使用F#函数类型，并创建使用委托作为实际F#实现。</span><span class="sxs-lookup"><span data-stu-id="e326b-394">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="e326b-395">使用 TryGetValue 模式而不是返回F#选项的值，并更喜欢方法重载采用到F#选项作为参数的值</span><span class="sxs-lookup"><span data-stu-id="e326b-395">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="e326b-396">有关使用的常见模式F#Api 中的选项类型为更好地实现在传统的.NET Api 使用标准.NET 设计技术。</span><span class="sxs-lookup"><span data-stu-id="e326b-396">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="e326b-397">而不是返回F#选项值，请考虑使用 bool 返回类型以及如"TryGetValue"模式中所示的输出参数。</span><span class="sxs-lookup"><span data-stu-id="e326b-397">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="e326b-398">和而不是采用F#选项作为参数的值，请考虑使用方法重载或可选参数。</span><span class="sxs-lookup"><span data-stu-id="e326b-398">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

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

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="e326b-399">使用.NET 集合接口类型 IEnumerable\<T\>和 IDictionary\<键，值\>参数和返回值</span><span class="sxs-lookup"><span data-stu-id="e326b-399">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="e326b-400">避免使用具体集合类型，如.NET 数组`T[]`，F#类型`list<T>`，`Map<Key,Value>`并`Set<T>`，以及.NET 具体集合类型，如`Dictionary<Key,Value>`。</span><span class="sxs-lookup"><span data-stu-id="e326b-400">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="e326b-401">.NET 类库设计准则有好的建议，有关何时使用各种集合类型，如`IEnumerable<T>`。</span><span class="sxs-lookup"><span data-stu-id="e326b-401">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="e326b-402">某些使用数组 (`T[]`) 是可以接受在某些情况下，性能的基础上。</span><span class="sxs-lookup"><span data-stu-id="e326b-402">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="e326b-403">请注意，尤其是`seq<T>`是只是F#别名以供`IEnumerable<T>`，并因此 seq 通常是一个普通的.NET API 的相应类型。</span><span class="sxs-lookup"><span data-stu-id="e326b-403">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="e326b-404">而不是F#列出了：</span><span class="sxs-lookup"><span data-stu-id="e326b-404">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names : string list) =
    ...
```

<span data-ttu-id="e326b-405">使用F#序列：</span><span class="sxs-lookup"><span data-stu-id="e326b-405">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="e326b-406">使用作为唯一的一种方法的输入类型的单位类型定义的零参数方法，或作为唯一返回类型来定义返回 void 的方法</span><span class="sxs-lookup"><span data-stu-id="e326b-406">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="e326b-407">避免单位类型的其他用法。</span><span class="sxs-lookup"><span data-stu-id="e326b-407">Avoid other uses of the unit type.</span></span> <span data-ttu-id="e326b-408">这些是很好：</span><span class="sxs-lookup"><span data-stu-id="e326b-408">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

<span data-ttu-id="e326b-409">这是错误的：</span><span class="sxs-lookup"><span data-stu-id="e326b-409">This is bad:</span></span>

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="e326b-410">检查在普通的.NET API 边界上的 null 值</span><span class="sxs-lookup"><span data-stu-id="e326b-410">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="e326b-411">F#实现代码往往具有较少的 null 值，原因不可变的设计模式和使用限制的 null 文本的F#类型。</span><span class="sxs-lookup"><span data-stu-id="e326b-411">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="e326b-412">其他.NET 语言通常使用 null 值频繁得多。</span><span class="sxs-lookup"><span data-stu-id="e326b-412">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="e326b-413">因此，F#公开了一个普通的.NET API 的代码应检查是否在 API 边界为空的参数和流动到更深入地阻止这些值F#实现代码。</span><span class="sxs-lookup"><span data-stu-id="e326b-413">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="e326b-414">`isNull`函数或模式进行匹配`null`，可以使用模式。</span><span class="sxs-lookup"><span data-stu-id="e326b-414">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="e326b-415">避免使用元组作为返回值</span><span class="sxs-lookup"><span data-stu-id="e326b-415">Avoid using tuples as return values</span></span>

<span data-ttu-id="e326b-416">相反，更倾向于返回命名的类型保存聚合数据，或使用 out 参数返回多个值。</span><span class="sxs-lookup"><span data-stu-id="e326b-416">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="e326b-417">尽管在.NET 中存在的元组和结构元组 （包括 C# 语言支持的结构元组），它们将最常提供理想和预期 API.NET 开发人员。</span><span class="sxs-lookup"><span data-stu-id="e326b-417">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="e326b-418">避免使用科的参数</span><span class="sxs-lookup"><span data-stu-id="e326b-418">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="e326b-419">请改用.NET 调用约定``Method(arg1,arg2,…,argN)``。</span><span class="sxs-lookup"><span data-stu-id="e326b-419">Instead, use .NET calling conventions ``Method(arg1,arg2,…,argN)``.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="e326b-420">提示:如果您正在设计用于从任何.NET 语言一样，使用库，则一些试验性是无可替代的实际执行的操作C#和 Visual Basic 编程，确保您的库"感觉右"从这些语言。</span><span class="sxs-lookup"><span data-stu-id="e326b-420">Tip: If you’re designing libraries for use from any .NET language, then there’s no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="e326b-421">此外可以使用.NET Reflector 和 Visual Studio 对象浏览器等工具来确保库和它们的文档显示预期的开发人员。</span><span class="sxs-lookup"><span data-stu-id="e326b-421">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="e326b-422">附录</span><span class="sxs-lookup"><span data-stu-id="e326b-422">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="e326b-423">设计的端到端示例F#以供其他.NET 语言代码</span><span class="sxs-lookup"><span data-stu-id="e326b-423">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="e326b-424">请考虑以下类：</span><span class="sxs-lookup"><span data-stu-id="e326b-424">Consider the following class:</span></span>

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

<span data-ttu-id="e326b-425">推断出F#的此类类型是按如下所示：</span><span class="sxs-lookup"><span data-stu-id="e326b-425">The inferred F# type of this class is as follows:</span></span>

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

<span data-ttu-id="e326b-426">让我们看一看这F#类型显示给使用另一种.NET 语言的程序员。</span><span class="sxs-lookup"><span data-stu-id="e326b-426">Let’s take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="e326b-427">例如，近似 C#"签名"是按如下所示：</span><span class="sxs-lookup"><span data-stu-id="e326b-427">For example, the approximate C# “signature” is as follows:</span></span>

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

<span data-ttu-id="e326b-428">有一些重要事项需要注意到有关如何F#表示此处构造。</span><span class="sxs-lookup"><span data-stu-id="e326b-428">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="e326b-429">例如：</span><span class="sxs-lookup"><span data-stu-id="e326b-429">For example:</span></span>

* <span data-ttu-id="e326b-430">保留元数据，例如参数名称。</span><span class="sxs-lookup"><span data-stu-id="e326b-430">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="e326b-431">F#方法采用两个自变量成为C#采用两个参数的方法。</span><span class="sxs-lookup"><span data-stu-id="e326b-431">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="e326b-432">函数和列表会变得对中的相应类型的引用F#库。</span><span class="sxs-lookup"><span data-stu-id="e326b-432">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="e326b-433">下面的代码演示如何调整该代码需要考虑这些内容。</span><span class="sxs-lookup"><span data-stu-id="e326b-433">The following code shows how to adjust this code to take these things into account.</span></span>

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

<span data-ttu-id="e326b-434">推断出F#类型的代码如下所示：</span><span class="sxs-lookup"><span data-stu-id="e326b-434">The inferred F# type of the code is as follows:</span></span>

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

<span data-ttu-id="e326b-435">C# 签名现在如下所示：</span><span class="sxs-lookup"><span data-stu-id="e326b-435">The C# signature is now as follows:</span></span>

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

<span data-ttu-id="e326b-436">进行了修复，以准备用于此类型，因为普通的.NET 库的一部分，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e326b-436">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="e326b-437">调整多个名称： `Point1`， `n`， `l`，和`f`变得`RadialPoint`， `count`， `factor`，和`transform`分别。</span><span class="sxs-lookup"><span data-stu-id="e326b-437">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="e326b-438">使用返回类型为`seq<RadialPoint>`而不是`RadialPoint list`通过更改列表构造使用`[ ... ]`序列构造使用`IEnumerable<RadialPoint>`。</span><span class="sxs-lookup"><span data-stu-id="e326b-438">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="e326b-439">使用.NET 委托类型`System.Func`而不是F#函数类型。</span><span class="sxs-lookup"><span data-stu-id="e326b-439">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="e326b-440">这样，就得好多了要在 C# 代码中使用。</span><span class="sxs-lookup"><span data-stu-id="e326b-440">This makes it far nicer to consume in C# code.</span></span>
