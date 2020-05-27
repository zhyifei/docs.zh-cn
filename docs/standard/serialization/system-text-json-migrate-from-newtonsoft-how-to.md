---
title: 从 Newtonsoft.Json 迁移到 System.Text.Json - .NET
author: ''
ms.author: ''
no-loc:
- System.Text.Json
- Newtonsoft.Json
ms.date: ''
helpviewer_keywords: []
ms.openlocfilehash: fe370b34d311816a815f3b2d419751ac7871f013
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703581"
---
# <a name="how-to-migrate-from-newtonsoftjson-to-systemtextjson"></a><span data-ttu-id="420a8-102">如何从 Newtonsoft.Json 迁移到 System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="420a8-102">How to migrate from Newtonsoft.Json to System.Text.Json</span></span>

<span data-ttu-id="420a8-103">本文演示如何从 [Newtonsoft.Json](https://www.newtonsoft.com/json) 迁移到 <xref:System.Text.Json>。</span><span class="sxs-lookup"><span data-stu-id="420a8-103">This article shows how to migrate from [Newtonsoft.Json](https://www.newtonsoft.com/json) to <xref:System.Text.Json>.</span></span>

<span data-ttu-id="420a8-104">`System.Text.Json` 命名空间提供用于序列化和反序列化 JavaScript 对象表示法 (JSON) 的功能。</span><span class="sxs-lookup"><span data-stu-id="420a8-104">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="420a8-105">`System.Text.Json` 库包含在 [.NET Core 3.0](https://aka.ms/netcore3download) 共享框架中。</span><span class="sxs-lookup"><span data-stu-id="420a8-105">The `System.Text.Json` library is included in the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span> <span data-ttu-id="420a8-106">对于其他目标框架，请安装 [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="420a8-106">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="420a8-107">包支持以下框架：</span><span class="sxs-lookup"><span data-stu-id="420a8-107">The package supports:</span></span>

* <span data-ttu-id="420a8-108">.NET Standard 2.0 及更高版本</span><span class="sxs-lookup"><span data-stu-id="420a8-108">.NET Standard 2.0 and later versions</span></span>
* <span data-ttu-id="420a8-109">.NET Framework 4.7.2 及更高版本</span><span class="sxs-lookup"><span data-stu-id="420a8-109">.NET Framework 4.7.2 and later versions</span></span>
* <span data-ttu-id="420a8-110">.NET Core 2.0、2.1 和 2.2</span><span class="sxs-lookup"><span data-stu-id="420a8-110">.NET Core 2.0, 2.1, and 2.2</span></span>

<span data-ttu-id="420a8-111">`System.Text.Json` 主要关注性能、安全性和标准符合性。</span><span class="sxs-lookup"><span data-stu-id="420a8-111">`System.Text.Json` focuses primarily on performance, security, and standards compliance.</span></span> <span data-ttu-id="420a8-112">它在默认行为方面有一些重要差异，不打算具有与 `Newtonsoft.Json` 相同的功能。</span><span class="sxs-lookup"><span data-stu-id="420a8-112">It has some key differences in default behavior and doesn't aim to have feature parity with `Newtonsoft.Json`.</span></span> <span data-ttu-id="420a8-113">对于某些方案，`System.Text.Json` 没有内置功能，但有建议解决方法。</span><span class="sxs-lookup"><span data-stu-id="420a8-113">For some scenarios, `System.Text.Json` has no built-in functionality, but there are recommended workarounds.</span></span> <span data-ttu-id="420a8-114">对于其他方案，解决方法是不切实际的。</span><span class="sxs-lookup"><span data-stu-id="420a8-114">For other scenarios, workarounds are impractical.</span></span> <span data-ttu-id="420a8-115">如果你的应用程序依赖于缺少的功能，请考虑[提交问题](https://github.com/dotnet/runtime/issues/new)以了解是否可以添加对你的方案的支持。</span><span class="sxs-lookup"><span data-stu-id="420a8-115">If your application depends on a missing feature, consider [filing an issue](https://github.com/dotnet/runtime/issues/new) to find out if support for your scenario can be added.</span></span>

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

<span data-ttu-id="420a8-116">本文的大部分内容介绍如何使用 <xref:System.Text.Json.JsonSerializer> API，不过也包含有关如何使用 <xref:System.Text.Json.JsonDocument>（表示文档对象模型或 DOM）、<xref:System.Text.Json.Utf8JsonReader> 和 <xref:System.Text.Json.Utf8JsonWriter> 类型的指导。</span><span class="sxs-lookup"><span data-stu-id="420a8-116">Most of this article is about how to use the <xref:System.Text.Json.JsonSerializer> API, but it also includes guidance on how to use the <xref:System.Text.Json.JsonDocument> (which represents the Document Object Model or DOM), <xref:System.Text.Json.Utf8JsonReader>, and <xref:System.Text.Json.Utf8JsonWriter> types.</span></span>

## <a name="table-of-differences-between-newtonsoftjson-and-systemtextjson"></a><span data-ttu-id="420a8-117">介绍 Newtonsoft.Json 与 System.Text.Json 之间差异的表格</span><span class="sxs-lookup"><span data-stu-id="420a8-117">Table of differences between Newtonsoft.Json and System.Text.Json</span></span>

<span data-ttu-id="420a8-118">下表列出 `Newtonsoft.Json` 功能和 `System.Text.Json` 等效功能。</span><span class="sxs-lookup"><span data-stu-id="420a8-118">The following table lists `Newtonsoft.Json` features and `System.Text.Json` equivalents.</span></span> <span data-ttu-id="420a8-119">这些等效功能分为以下类别：</span><span class="sxs-lookup"><span data-stu-id="420a8-119">The equivalents fall into the following categories:</span></span>

* <span data-ttu-id="420a8-120">受支持功能支持。</span><span class="sxs-lookup"><span data-stu-id="420a8-120">Supported by built-in functionality.</span></span> <span data-ttu-id="420a8-121">从 `System.Text.Json` 获取类似行为可能需要使用特性或全局选项。</span><span class="sxs-lookup"><span data-stu-id="420a8-121">Getting similar behavior from `System.Text.Json` may require the use of an attribute or global option.</span></span>
* <span data-ttu-id="420a8-122">不受支持，可能有解决方法。</span><span class="sxs-lookup"><span data-stu-id="420a8-122">Not supported, workaround is possible.</span></span> <span data-ttu-id="420a8-123">解决方法是[自定义转换器](system-text-json-converters-how-to.md)，它们可能无法提供与 `Newtonsoft.Json` 功能完全相同的功能。</span><span class="sxs-lookup"><span data-stu-id="420a8-123">The workarounds are [custom converters](system-text-json-converters-how-to.md), which may not provide complete parity with `Newtonsoft.Json` functionality.</span></span> <span data-ttu-id="420a8-124">对于其中一些功能，提供示例代码作为示例。</span><span class="sxs-lookup"><span data-stu-id="420a8-124">For some of these, sample code is provided as examples.</span></span> <span data-ttu-id="420a8-125">如果你依赖于这些 `Newtonsoft.Json` 功能，迁移需要修改 .NET 对象模型或进行其他代码更改。</span><span class="sxs-lookup"><span data-stu-id="420a8-125">If you rely on these `Newtonsoft.Json` features, migration will require modifications to your .NET object models or other code changes.</span></span>
* <span data-ttu-id="420a8-126">不受支持，解决方法不可行或无法提供。</span><span class="sxs-lookup"><span data-stu-id="420a8-126">Not supported, workaround is not practical or possible.</span></span> <span data-ttu-id="420a8-127">如果你依赖于这些 `Newtonsoft.Json` 功能，则无法在不进行重大更改的情况下进行迁移。</span><span class="sxs-lookup"><span data-stu-id="420a8-127">If you rely on these `Newtonsoft.Json` features, migration will not be possible without significant changes.</span></span>

| Newtonsoft.Json<span data-ttu-id="420a8-128"> 功能</span><span class="sxs-lookup"><span data-stu-id="420a8-128"> feature</span></span>                               | System.Text.Json<span data-ttu-id="420a8-129"> 等效</span><span class="sxs-lookup"><span data-stu-id="420a8-129"> equivalent</span></span> |
|---
<span data-ttu-id="420a8-130">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-130">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-131">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-131">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-132">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-132">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-133">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-133">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-134">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-134">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-135">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-135">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-136">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-136">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-137">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-137">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-138">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-138">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-139">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-139">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-140">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-140">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-141">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-141">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-142">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-142">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-143">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-143">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-144">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-144">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-145">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-145">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-146">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-146">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-147">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-147">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-148">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-148">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-149">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-149">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-150">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-150">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-151">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-151">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-152">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-152">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-153">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-153">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-154">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-154">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-155">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-155">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-156">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-156">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-157">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-157">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-158">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-158">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-159">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-159">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-160">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-160">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-161">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-161">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-162">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-162">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-163">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-163">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-164">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-164">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-165">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-165">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-166">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-166">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-167">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-167">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-168">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-168">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-169">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-169">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-170">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-170">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-171">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-171">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-172">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-172">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-173">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-173">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-174">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-174">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-175">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-175">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-176">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-176">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-177">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-177">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-178">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-178">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-179">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-179">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-180">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-180">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-181">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-181">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-182">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-182">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-183">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-183">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-184">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-184">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-185">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-185">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-186">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-186">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-187">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-187">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-188">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-188">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-189">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-189">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-190">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-190">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-191">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-191">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-192">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-192">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-193">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-193">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-194">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-194">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-195">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-195">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-196">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-196">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-197">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-197">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-198">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-198">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-199">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-199">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-200">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-200">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-201">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-201">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-202">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-202">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-203">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-203">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-204">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-204">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="420a8-205">----------------------------|--- title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-205">----------------------------|--- title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-206">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-206">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-207">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-207">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-208">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-208">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-209">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-209">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-210">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-210">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-211">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-211">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-212">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-212">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-213">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-213">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-214">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-214">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-215">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-215">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-216">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-216">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-217">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-217">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-218">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-218">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-219">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-219">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-220">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-220">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-221">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-221">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-222">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-222">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-223">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-223">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-224">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-224">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-225">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-225">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-226">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-226">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-227">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-227">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-228">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-228">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-229">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-229">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-230">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-230">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-231">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-231">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-232">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-232">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-233">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-233">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-234">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-234">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-235">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-235">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-236">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-236">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-237">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-237">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="420a8-238">title:'从 Newtonsoft.Json 迁移到 System.Text.Json - .NET' author: ms.author: no-loc:</span><span class="sxs-lookup"><span data-stu-id="420a8-238">title: 'Migrate from Newtonsoft.Json to System.Text.Json - .NET' author: ms.author: no-loc:</span></span>
- <span data-ttu-id="420a8-239">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="420a8-239">'System.Text.Json'</span></span>
- <span data-ttu-id="420a8-240">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="420a8-240">'Newtonsoft.Json' ms.date: helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="420a8-241">---------------| | 默认情况下不区分大小写的反序列化           | ✔️ [PropertyNameCaseInsensitive 全局设置](#case-insensitive-deserialization) | | Camel-case 属性名                             | ✔️ [PropertyNamingPolicy 全局设置](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) | | 最小字符转义                            | ✔️ [严格字符转义，可配置](#minimal-character-escaping) | | `NullValueHandling.Ignore` 全局设置             | ✔️ [IgnoreNullValues 全局选项](system-text-json-how-to.md#exclude-all-null-value-properties) | | 允许注释                                        | ✔️ [ReadCommentHandling 全局设置](#comments) | | 允许尾随逗号                                | ✔️ [AllowTrailingCommas 全局设置](#trailing-commas) | | 自定义转换器注册                         | ✔️ [优先顺序不同](#converter-registration-precedence) | | 无默认最大深度                           | ✔️ [默认最大深度 64，可配置](#maximum-depth) | | 支持多种类型                    | ⚠️ [某些类型需要自定义转换器](#types-without-built-in-support) | | 将字符串反序列化为数字                        | ⚠️ [不支持，解决方法，示例](#quoted-numbers) | | 使用非字符串键反序列化 `Dictionary`          | ⚠️ [不支持，解决方法，示例](#dictionary-with-non-string-key) | | 多态序列化                             | ⚠️ [不支持，解决方法，示例](#polymorphic-serialization) | | 多态序列化                           | ⚠️ [不支持，解决方法，示例](#polymorphic-deserialization) | | 将推断类型反序列化为 `object` 属性      | ⚠️ [不支持，解决方法，示例](#deserialization-of-object-properties) | | 将 JSON `null` 文本反序列化为不可为 null 的值类型 | ⚠️ [不支持，解决方法，示例](#deserialize-null-to-non-nullable-type) | | 反序列化为不可变类和结构          | ⚠️ [不支持，解决方法，示例](#deserialize-to-immutable-classes-and-structs) | | `[JsonConstructor]` 特性                         | ⚠️ [不支持，解决方法，示例](#specify-constructor-to-use) | | `[JsonProperty]` 特性上的 `Required` 设置        | ⚠️ [不支持，解决方法，示例](#required-properties) | | `[JsonProperty]` 特性上的 `NullValueHandling` 设置 | ⚠️ [不支持，解决方法，示例](#conditionally-ignore-a-property)  | | `[JsonProperty]` 特性上的 `DefaultValueHandling` 设置 | ⚠️ [不支持，解决方法，示例](#conditionally-ignore-a-property)  | | `DefaultValueHandling` 全局设置                 | ⚠️ [不支持，解决方法，示例](#conditionally-ignore-a-property) | | 用于排除属性的 `DefaultContractResolver`       | ⚠️ [不支持，解决方法，示例](#conditionally-ignore-a-property) | | `DateTimeZoneHandling`、`DateFormatString` 设置   | ⚠️ [不支持，解决方法，示例](#specify-date-format) | | 回调                                             | ⚠️ [不支持，解决方法，示例](#callbacks) | | 对公共和非公共字段的支持              | ⚠️ [不支持，解决方法](#public-and-non-public-fields) | | 对内部和专用属性 setter 和 getter 的支持 | ⚠️ [不支持，解决方法](#internal-and-private-property-setters-and-getters) | | `JsonConvert.PopulateObject` 方法                   | ⚠️ [不支持，解决方法](#populate-existing-objects) | | `ObjectCreationHandling` 全局设置               | ⚠️ [不支持，解决方法](#reuse-rather-than-replace-properties) | | 添加到无 setter 的集合                    | ⚠️ [不支持，解决方法](#add-to-collections-without-setters) | | `PreserveReferencesHandling` 全局设置           | ❌ [不支持](#preserve-object-references-and-handle-loops) | | `ReferenceLoopHandling` 全局设置                | ❌ [不支持](#preserve-object-references-and-handle-loops) | | 对 `System.Runtime.Serialization` 特性的支持 | ❌ [不支持](#systemruntimeserialization-attributes) | | `MissingMemberHandling` 全局设置                | ❌ [不支持](#missingmemberhandling) | | 允许属性名不加引号                   | ❌ [不支持](#json-strings-property-names-and-string-values) | | 允许在字符串值周围使用单引号              | ❌ [不支持](#json-strings-property-names-and-string-values) | | 允许为字符串属性使用非字符串 JSON 值    | ❌ [不支持](#non-string-values-for-string-properties) |</span><span class="sxs-lookup"><span data-stu-id="420a8-241">---------------| | Case-insensitive deserialization by default           | ✔️ [PropertyNameCaseInsensitive global setting](#case-insensitive-deserialization) | | Camel-case property names                             | ✔️ [PropertyNamingPolicy global setting](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) | | Minimal character escaping                            | ✔️ [Strict character escaping, configurable](#minimal-character-escaping) | | `NullValueHandling.Ignore` global setting             | ✔️ [IgnoreNullValues global option](system-text-json-how-to.md#exclude-all-null-value-properties) | | Allow comments                                        | ✔️ [ReadCommentHandling global setting](#comments) | | Allow trailing commas                                 | ✔️ [AllowTrailingCommas global setting](#trailing-commas) | | Custom converter registration                         | ✔️ [Order of precedence differs](#converter-registration-precedence) | | No maximum depth by default                           | ✔️ [Default maximum depth 64, configurable](#maximum-depth) | | Support for a broad range of types                    | ⚠️ [Some types require custom converters](#types-without-built-in-support) | | Deserialize strings as numbers                        | ⚠️ [Not supported, workaround, sample](#quoted-numbers) | | Deserialize `Dictionary` with non-string key          | ⚠️ [Not supported, workaround, sample](#dictionary-with-non-string-key) | | Polymorphic serialization                             | ⚠️ [Not supported, workaround, sample](#polymorphic-serialization) | | Polymorphic deserialization                           | ⚠️ [Not supported, workaround, sample](#polymorphic-deserialization) | | Deserialize inferred type to `object` properties      | ⚠️ [Not supported, workaround, sample](#deserialization-of-object-properties) | | Deserialize JSON `null` literal to non-nullable value types | ⚠️ [Not supported, workaround, sample](#deserialize-null-to-non-nullable-type) | | Deserialize to immutable classes and structs          | ⚠️ [Not supported, workaround, sample](#deserialize-to-immutable-classes-and-structs) | | `[JsonConstructor]` attribute                         | ⚠️ [Not supported, workaround, sample](#specify-constructor-to-use) | | `Required` setting on `[JsonProperty]` attribute        | ⚠️ [Not supported, workaround, sample](#required-properties) | | `NullValueHandling` setting on `[JsonProperty]` attribute | ⚠️ [Not supported, workaround, sample](#conditionally-ignore-a-property)  | | `DefaultValueHandling` setting on `[JsonProperty]` attribute | ⚠️ [Not supported, workaround, sample](#conditionally-ignore-a-property)  | | `DefaultValueHandling` global setting                 | ⚠️ [Not supported, workaround, sample](#conditionally-ignore-a-property) | | `DefaultContractResolver` to exclude properties       | ⚠️ [Not supported, workaround, sample](#conditionally-ignore-a-property) | | `DateTimeZoneHandling`, `DateFormatString` settings   | ⚠️ [Not supported, workaround, sample](#specify-date-format) | | Callbacks                                             | ⚠️ [Not supported, workaround, sample](#callbacks) | | Support for public and non-public fields              | ⚠️ [Not supported, workaround](#public-and-non-public-fields) | | Support for internal and private property setters and getters | ⚠️ [Not supported, workaround](#internal-and-private-property-setters-and-getters) | | `JsonConvert.PopulateObject` method                   | ⚠️ [Not supported, workaround](#populate-existing-objects) | | `ObjectCreationHandling` global setting               | ⚠️ [Not supported, workaround](#reuse-rather-than-replace-properties) | | Add to collections without setters                    | ⚠️ [Not supported, workaround](#add-to-collections-without-setters) | | `PreserveReferencesHandling` global setting           | ❌ [Not supported](#preserve-object-references-and-handle-loops) | | `ReferenceLoopHandling` global setting                | ❌ [Not supported](#preserve-object-references-and-handle-loops) | | Support for `System.Runtime.Serialization` attributes | ❌ [Not supported](#systemruntimeserialization-attributes) | | `MissingMemberHandling` global setting                | ❌ [Not supported](#missingmemberhandling) | | Allow property names without quotes                   | ❌ [Not supported](#json-strings-property-names-and-string-values) | | Allow single quotes around string values              | ❌ [Not supported](#json-strings-property-names-and-string-values) | | Allow non-string JSON values for string properties    | ❌ [Not supported](#non-string-values-for-string-properties) |</span></span>

<span data-ttu-id="420a8-242">这不是 `Newtonsoft.Json` 功能的详尽列表。</span><span class="sxs-lookup"><span data-stu-id="420a8-242">This is not an exhaustive list of `Newtonsoft.Json` features.</span></span> <span data-ttu-id="420a8-243">此列表包含在 [GitHub 问题](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)或 [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json) 文章中请求的许多方案。</span><span class="sxs-lookup"><span data-stu-id="420a8-243">The list includes many of the scenarios that have been requested in [GitHub issues](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) or [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json) posts.</span></span> <span data-ttu-id="420a8-244">如果对此处所列且当前没有示例代码的一个方案实现了解决方法，并且如果要共享解决方案，请在本页底部的“反馈”部分选择“此页面”。</span><span class="sxs-lookup"><span data-stu-id="420a8-244">If you implement a workaround for one of the scenarios listed here that doesn't currently have sample code, and if you want to share your solution, select **This page** in the **Feedback** section at the bottom of this page.</span></span> <span data-ttu-id="420a8-245">这会在本文档的 GitHub 存储库中创建一个问题，并将它也列在此页面上的“反馈”部分中。</span><span class="sxs-lookup"><span data-stu-id="420a8-245">That creates an issue in this documentation's GitHub repo and lists it in the **Feedback** section on this page too.</span></span>

## <a name="differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson"></a><span data-ttu-id="420a8-246">默认 JsonSerializer 行为相较于 Newtonsoft.Json 的差异</span><span class="sxs-lookup"><span data-stu-id="420a8-246">Differences in default JsonSerializer behavior compared to Newtonsoft.Json</span></span>

<span data-ttu-id="420a8-247"><xref:System.Text.Json> 在默认情况下十分严格，避免代表调用方进行任何猜测或解释，强调确定性行为。</span><span class="sxs-lookup"><span data-stu-id="420a8-247"><xref:System.Text.Json> is strict by default and avoids any guessing or interpretation on the caller's behalf, emphasizing deterministic behavior.</span></span> <span data-ttu-id="420a8-248">该库是为了实现性能和安全性而特意这样设计的。</span><span class="sxs-lookup"><span data-stu-id="420a8-248">The library is intentionally designed this way for performance and security.</span></span> <span data-ttu-id="420a8-249">`Newtonsoft.Json` 默认情况下十分灵活。</span><span class="sxs-lookup"><span data-stu-id="420a8-249">`Newtonsoft.Json` is flexible by default.</span></span> <span data-ttu-id="420a8-250">设计中的这种根本差异是默认行为中以下许多特定差异的背后原因。</span><span class="sxs-lookup"><span data-stu-id="420a8-250">This fundamental difference in design is behind many of the following specific differences in default behavior.</span></span>

### <a name="case-insensitive-deserialization"></a><span data-ttu-id="420a8-251">不区分大小写的反序列化</span><span class="sxs-lookup"><span data-stu-id="420a8-251">Case-insensitive deserialization</span></span>

<span data-ttu-id="420a8-252">在反序列化过程中，默认情况下 `Newtonsoft.Json` 进行不区分大小写的属性名称匹配。</span><span class="sxs-lookup"><span data-stu-id="420a8-252">During deserialization, `Newtonsoft.Json` does case-insensitive property name matching by default.</span></span> <span data-ttu-id="420a8-253"><xref:System.Text.Json> 默认值区分大小写，这可提供更好的性能，因为它执行精确匹配。</span><span class="sxs-lookup"><span data-stu-id="420a8-253">The <xref:System.Text.Json> default is case-sensitive, which gives better performance since it's doing an exact match.</span></span> <span data-ttu-id="420a8-254">有关如何执行不区分大小写的匹配的信息，请参阅[不区分大小写的属性匹配](system-text-json-how-to.md#case-insensitive-property-matching)。</span><span class="sxs-lookup"><span data-stu-id="420a8-254">For information about how to do case-insensitive matching, see [Case-insensitive property matching](system-text-json-how-to.md#case-insensitive-property-matching).</span></span>

<span data-ttu-id="420a8-255">如果使用 ASP.NET Core 间接使用 `System.Text.Json`，则无需执行任何操作即可获得类似于 `Newtonsoft.Json` 的行为。</span><span class="sxs-lookup"><span data-stu-id="420a8-255">If you're using `System.Text.Json` indirectly by using ASP.NET Core, you don't need to do anything to get behavior like `Newtonsoft.Json`.</span></span> <span data-ttu-id="420a8-256">ASP.NET Core 在使用 `System.Text.Json` 时，会为 [camel 大小写属性名称](system-text-json-how-to.md#use-camel-case-for-all-json-property-names)和不区分大小写的匹配指定设置。</span><span class="sxs-lookup"><span data-stu-id="420a8-256">ASP.NET Core specifies the settings for [camel-casing property names](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) and case-insensitive matching when it uses `System.Text.Json`.</span></span>

### <a name="minimal-character-escaping"></a><span data-ttu-id="420a8-257">最小字符转义</span><span class="sxs-lookup"><span data-stu-id="420a8-257">Minimal character escaping</span></span>

<span data-ttu-id="420a8-258">在序列化过程中，`Newtonsoft.Json` 对于让字符通过而不进行转义相对宽松。</span><span class="sxs-lookup"><span data-stu-id="420a8-258">During serialization, `Newtonsoft.Json` is relatively permissive about letting characters through without escaping them.</span></span> <span data-ttu-id="420a8-259">也就是说，它不会将它们替换为 `\uxxxx`（其中 `xxxx` 是字符的码位）。</span><span class="sxs-lookup"><span data-stu-id="420a8-259">That is, it doesn't replace them with `\uxxxx` where `xxxx` is the character's code point.</span></span> <span data-ttu-id="420a8-260">对字符进行转义时，它会通过在字符前发出 `\` 来实现此目的（例如，`"` 会变为 `\"`）。</span><span class="sxs-lookup"><span data-stu-id="420a8-260">Where it does escape them, it does so by emitting a `\` before the character (for example, `"` becomes `\"`).</span></span> <span data-ttu-id="420a8-261"><xref:System.Text.Json> 会在默认情况下转义较多字符，以对跨站点脚本 (XSS) 或信息泄露攻击提供深度防御保护，并使用六字符序列执行此操作。</span><span class="sxs-lookup"><span data-stu-id="420a8-261"><xref:System.Text.Json> escapes more characters by default to provide defense-in-depth protections against cross-site scripting (XSS) or information-disclosure attacks and does so by using the six-character sequence.</span></span> <span data-ttu-id="420a8-262">`System.Text.Json` 会在默认情况下转义所有非 ASCII 字符，因此如果在 `Newtonsoft.Json` 中使用 `StringEscapeHandling.EscapeNonAscii`，则无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="420a8-262">`System.Text.Json` escapes all non-ASCII characters by default, so you don't need to do anything if you're using `StringEscapeHandling.EscapeNonAscii` in `Newtonsoft.Json`.</span></span> <span data-ttu-id="420a8-263">`System.Text.Json` 在默认情况下还会转义 HTML 敏感字符。</span><span class="sxs-lookup"><span data-stu-id="420a8-263">`System.Text.Json` also escapes HTML-sensitive characters, by default.</span></span> <span data-ttu-id="420a8-264">有关如何替代默认 `System.Text.Json` 行为的信息，请参阅[自定义字符编码](system-text-json-how-to.md#customize-character-encoding)。</span><span class="sxs-lookup"><span data-stu-id="420a8-264">For information about how to override the default `System.Text.Json` behavior, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="comments"></a><span data-ttu-id="420a8-265">注释</span><span class="sxs-lookup"><span data-stu-id="420a8-265">Comments</span></span>

<span data-ttu-id="420a8-266">在反序列化过程中，`Newtonsoft.Json` 在默认情况下会忽略 JSON 中的注释。</span><span class="sxs-lookup"><span data-stu-id="420a8-266">During deserialization, `Newtonsoft.Json` ignores comments in the JSON by default.</span></span> <span data-ttu-id="420a8-267"><xref:System.Text.Json> 默认值是对注释引发异常，因为 [RFC 8259](https://tools.ietf.org/html/rfc8259) 规范不包含它们。</span><span class="sxs-lookup"><span data-stu-id="420a8-267">The <xref:System.Text.Json> default is to throw exceptions for comments because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't include them.</span></span> <span data-ttu-id="420a8-268">有关如何允许注释的信息，请参阅[允许注释和尾随逗号](system-text-json-how-to.md#allow-comments-and-trailing-commas)。</span><span class="sxs-lookup"><span data-stu-id="420a8-268">For information about how to allow comments, see [Allow comments and trailing commas](system-text-json-how-to.md#allow-comments-and-trailing-commas).</span></span>

### <a name="trailing-commas"></a><span data-ttu-id="420a8-269">尾随逗号</span><span class="sxs-lookup"><span data-stu-id="420a8-269">Trailing commas</span></span>

<span data-ttu-id="420a8-270">在反序列化过程中，默认情况下 `Newtonsoft.Json` 会忽略尾随逗号。</span><span class="sxs-lookup"><span data-stu-id="420a8-270">During deserialization, `Newtonsoft.Json` ignores trailing commas by default.</span></span> <span data-ttu-id="420a8-271">它还会忽略多个尾随逗号（例如 `[{"Color":"Red"},{"Color":"Green"},,]`）。</span><span class="sxs-lookup"><span data-stu-id="420a8-271">It also ignores multiple trailing commas (for example, `[{"Color":"Red"},{"Color":"Green"},,]`).</span></span> <span data-ttu-id="420a8-272"><xref:System.Text.Json> 默认值是对尾随逗号引发异常，因为 [RFC 8259](https://tools.ietf.org/html/rfc8259) 规范不允许使用它们。</span><span class="sxs-lookup"><span data-stu-id="420a8-272">The <xref:System.Text.Json> default is to throw exceptions for trailing commas because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't allow them.</span></span> <span data-ttu-id="420a8-273">有关如何使 `System.Text.Json` 接受它们的信息，请参阅[允许注释和尾随逗号](system-text-json-how-to.md#allow-comments-and-trailing-commas)。</span><span class="sxs-lookup"><span data-stu-id="420a8-273">For information about how to make `System.Text.Json` accept them, see [Allow comments and trailing commas](system-text-json-how-to.md#allow-comments-and-trailing-commas).</span></span> <span data-ttu-id="420a8-274">无法允许多个尾随逗号。</span><span class="sxs-lookup"><span data-stu-id="420a8-274">There's no way to allow multiple trailing commas.</span></span>

### <a name="converter-registration-precedence"></a><span data-ttu-id="420a8-275">转换器注册优先级</span><span class="sxs-lookup"><span data-stu-id="420a8-275">Converter registration precedence</span></span>

<span data-ttu-id="420a8-276">自定义转换器的 `Newtonsoft.Json` 注册优先级如下所示：</span><span class="sxs-lookup"><span data-stu-id="420a8-276">The `Newtonsoft.Json` registration precedence for custom converters is as follows:</span></span>

* <span data-ttu-id="420a8-277">属性上的特性</span><span class="sxs-lookup"><span data-stu-id="420a8-277">Attribute on property</span></span>
* <span data-ttu-id="420a8-278">类型上的特性</span><span class="sxs-lookup"><span data-stu-id="420a8-278">Attribute on type</span></span>
* <span data-ttu-id="420a8-279">[转换器](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm) 集合</span><span class="sxs-lookup"><span data-stu-id="420a8-279">[Converters](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm) collection</span></span>

<span data-ttu-id="420a8-280">此顺序意味着 `Converters` 集合中的自定义转换器会由通过在类型级别应用特性而注册的转换器替代。</span><span class="sxs-lookup"><span data-stu-id="420a8-280">This order means that a custom converter in the `Converters` collection is overridden by a converter that is registered by applying an attribute at the type level.</span></span> <span data-ttu-id="420a8-281">这两个注册都会由属性级别的特性替代。</span><span class="sxs-lookup"><span data-stu-id="420a8-281">Both of those registrations are overridden by an attribute at the property level.</span></span>

<span data-ttu-id="420a8-282">自定义转换器的 <xref:System.Text.Json> 注册优先级是不同的：</span><span class="sxs-lookup"><span data-stu-id="420a8-282">The <xref:System.Text.Json> registration precedence for custom converters is different:</span></span>

* <span data-ttu-id="420a8-283">属性上的特性</span><span class="sxs-lookup"><span data-stu-id="420a8-283">Attribute on property</span></span>
* <span data-ttu-id="420a8-284"><xref:System.Text.Json.JsonSerializerOptions.Converters> 集合</span><span class="sxs-lookup"><span data-stu-id="420a8-284"><xref:System.Text.Json.JsonSerializerOptions.Converters> collection</span></span>
* <span data-ttu-id="420a8-285">类型上的特性</span><span class="sxs-lookup"><span data-stu-id="420a8-285">Attribute on type</span></span>

<span data-ttu-id="420a8-286">此处的差别在于 `Converters` 集合中的自定义转换器会替代类型级别的特性。</span><span class="sxs-lookup"><span data-stu-id="420a8-286">The difference here is that a custom converter in the `Converters` collection overrides an attribute at the type level.</span></span> <span data-ttu-id="420a8-287">此优先级顺序的目的是使运行时更改替代设计时选项。</span><span class="sxs-lookup"><span data-stu-id="420a8-287">The intention behind this order of precedence is to make run-time changes override design-time choices.</span></span> <span data-ttu-id="420a8-288">无法更改优先级。</span><span class="sxs-lookup"><span data-stu-id="420a8-288">There's no way to change the precedence.</span></span>

<span data-ttu-id="420a8-289">有关自定义转换器注册的详细信息，请参阅[注册自定义转换器](system-text-json-converters-how-to.md#register-a-custom-converter)。</span><span class="sxs-lookup"><span data-stu-id="420a8-289">For more information about custom converter registration, see [Register a custom converter](system-text-json-converters-how-to.md#register-a-custom-converter).</span></span>

### <a name="maximum-depth"></a><span data-ttu-id="420a8-290">最大深度</span><span class="sxs-lookup"><span data-stu-id="420a8-290">Maximum depth</span></span>

<span data-ttu-id="420a8-291">`Newtonsoft.Json` 默认情况下没有最大深度限制。</span><span class="sxs-lookup"><span data-stu-id="420a8-291">`Newtonsoft.Json` doesn't have a maximum depth limit by default.</span></span> <span data-ttu-id="420a8-292">对于 <xref:System.Text.Json>，默认限制为 64，可通过设置 <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType> 进行配置。</span><span class="sxs-lookup"><span data-stu-id="420a8-292">For <xref:System.Text.Json> there's a default limit  of 64, and it's configurable by setting <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>.</span></span>

### <a name="json-strings-property-names-and-string-values"></a><span data-ttu-id="420a8-293">JSON 字符串（属性名称和字符串值）</span><span class="sxs-lookup"><span data-stu-id="420a8-293">JSON strings (property names and string values)</span></span>

<span data-ttu-id="420a8-294">在反序列化过程中，`Newtonsoft.Json` 接受用双引号、单引号括起来或不带引号的属性名称。</span><span class="sxs-lookup"><span data-stu-id="420a8-294">During deserialization, `Newtonsoft.Json` accepts property names surrounded by double quotes, single quotes, or without quotes.</span></span> <span data-ttu-id="420a8-295">它接受用双引号或单引号括起来的字符串值。</span><span class="sxs-lookup"><span data-stu-id="420a8-295">It accepts string values surrounded by double quotes or single quotes.</span></span> <span data-ttu-id="420a8-296">例如，`Newtonsoft.Json` 接受以下 JSON：</span><span class="sxs-lookup"><span data-stu-id="420a8-296">For example, `Newtonsoft.Json` accepts the following JSON:</span></span>

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

<span data-ttu-id="420a8-297">`System.Text.Json` 仅接受双引号中的属性名称和字符串值，因为 [RFC 8259](https://tools.ietf.org/html/rfc8259) 规范要求使用该格式，这是唯一视为有效 JSON 的格式。</span><span class="sxs-lookup"><span data-stu-id="420a8-297">`System.Text.Json` only accepts property names and string values in double quotes because that format is required by the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification and is the only format considered valid JSON.</span></span>

<span data-ttu-id="420a8-298">用单引号括起来的值会导致 [JsonException](xref:System.Text.Json.JsonException)，并出现以下消息：</span><span class="sxs-lookup"><span data-stu-id="420a8-298">A value enclosed in single quotes results in a [JsonException](xref:System.Text.Json.JsonException) with the following message:</span></span>

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a><span data-ttu-id="420a8-299">字符串属性的非字符串值</span><span class="sxs-lookup"><span data-stu-id="420a8-299">Non-string values for string properties</span></span>

<span data-ttu-id="420a8-300">`Newtonsoft.Json` 接受非字符串值（如数字或文本 `true` 和 `false`），以便反序列化为类型字符串的属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-300">`Newtonsoft.Json` accepts non-string values, such as a number or the literals `true` and `false`, for deserialization to properties of type string.</span></span> <span data-ttu-id="420a8-301">下面是 `Newtonsoft.Json` 成功反序列化为以下类的 JSON 示例：</span><span class="sxs-lookup"><span data-stu-id="420a8-301">Here's an example of JSON that `Newtonsoft.Json` successfully deserializes to the following class:</span></span>

```json
{
  "String1": 1,
  "String2": true,
  "String3": false
}
```

```csharp
public class ExampleClass
{
    public string String1 { get; set; }
    public string String2 { get; set; }
    public string String3 { get; set; }
}
```

<span data-ttu-id="420a8-302">`System.Text.Json` 不将非字符串值反序列化为字符串属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-302">`System.Text.Json` doesn't deserialize non-string values into string properties.</span></span> <span data-ttu-id="420a8-303">字符串字段接收的非字符串值会导致 [JsonException](xref:System.Text.Json.JsonException)，并出现以下消息：</span><span class="sxs-lookup"><span data-stu-id="420a8-303">A non-string value received for a string field results in a [JsonException](xref:System.Text.Json.JsonException) with the following message:</span></span>

```
The JSON value could not be converted to System.String.
```

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a><span data-ttu-id="420a8-304">使用 JsonSerializer 且需要解决方法的方案</span><span class="sxs-lookup"><span data-stu-id="420a8-304">Scenarios using JsonSerializer that require workarounds</span></span>

<span data-ttu-id="420a8-305">以下方案不受内置功能支持，但有解决方法可用。</span><span class="sxs-lookup"><span data-stu-id="420a8-305">The following scenarios aren't supported by built-in functionality, but workarounds are possible.</span></span> <span data-ttu-id="420a8-306">解决方法是[自定义转换器](system-text-json-converters-how-to.md)，它们可能无法提供与 `Newtonsoft.Json` 功能完全相同的功能。</span><span class="sxs-lookup"><span data-stu-id="420a8-306">The workarounds are [custom converters](system-text-json-converters-how-to.md), which may not provide complete parity with `Newtonsoft.Json` functionality.</span></span> <span data-ttu-id="420a8-307">对于其中一些功能，提供示例代码作为示例。</span><span class="sxs-lookup"><span data-stu-id="420a8-307">For some of these, sample code is provided as examples.</span></span> <span data-ttu-id="420a8-308">如果你依赖于这些 `Newtonsoft.Json` 功能，迁移需要修改 .NET 对象模型或进行其他代码更改。</span><span class="sxs-lookup"><span data-stu-id="420a8-308">If you rely on these `Newtonsoft.Json` features, migration will require modifications to your .NET object models or other code changes.</span></span>

### <a name="types-without-built-in-support"></a><span data-ttu-id="420a8-309">没有内置支持的类型</span><span class="sxs-lookup"><span data-stu-id="420a8-309">Types without built-in support</span></span>

<span data-ttu-id="420a8-310"><xref:System.Text.Json> 不为以下类型提供内置支持：</span><span class="sxs-lookup"><span data-stu-id="420a8-310"><xref:System.Text.Json> doesn't provide built-in support for the following types:</span></span>

* <span data-ttu-id="420a8-311"><xref:System.Data.DataTable> 和相关类型</span><span class="sxs-lookup"><span data-stu-id="420a8-311"><xref:System.Data.DataTable> and related types</span></span>
* <span data-ttu-id="420a8-312">F# 类型（如[可区分联合](../../fsharp/language-reference/discriminated-unions.md)、[记录类型](../../fsharp/language-reference/records.md)和[匿名记录类型](../../fsharp/language-reference/anonymous-records.md)）。</span><span class="sxs-lookup"><span data-stu-id="420a8-312">F# types, such as [discriminated unions](../../fsharp/language-reference/discriminated-unions.md), [record types](../../fsharp/language-reference/records.md), and [anonymous record types](../../fsharp/language-reference/anonymous-records.md).</span></span>
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <span data-ttu-id="420a8-313"><xref:System.ValueTuple> 及其关联泛型类型</span><span class="sxs-lookup"><span data-stu-id="420a8-313"><xref:System.ValueTuple> and its associated generic types</span></span>

<span data-ttu-id="420a8-314">对于没有内置支持的类型，可以实现自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="420a8-314">Custom converters can be implemented for types that don't have built-in support.</span></span>

### <a name="quoted-numbers"></a><span data-ttu-id="420a8-315">带引号的数字</span><span class="sxs-lookup"><span data-stu-id="420a8-315">Quoted numbers</span></span>

<span data-ttu-id="420a8-316">`Newtonsoft.Json` 可以序列化或反序列化由 JSON 字符串表示的数字（括在引号中）。</span><span class="sxs-lookup"><span data-stu-id="420a8-316">`Newtonsoft.Json` can serialize or deserialize numbers represented by JSON strings (surrounded by quotes).</span></span> <span data-ttu-id="420a8-317">例如，它可以接受 `{"DegreesCelsius":"23"}` 而不是 `{"DegreesCelsius":23}`。</span><span class="sxs-lookup"><span data-stu-id="420a8-317">For example, it can accept: `{"DegreesCelsius":"23"}` instead of `{"DegreesCelsius":23}`.</span></span> <span data-ttu-id="420a8-318">若要在 <xref:System.Text.Json> 中启用该行为，请实现类似于以下示例的自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="420a8-318">To enable that behavior in <xref:System.Text.Json>, implement a custom converter like the following example.</span></span> <span data-ttu-id="420a8-319">该转换器处理定义为 `long` 的属性：</span><span class="sxs-lookup"><span data-stu-id="420a8-319">The converter handles properties defined as `long`:</span></span>

* <span data-ttu-id="420a8-320">它将这些属性序列化为 JSON 字符串。</span><span class="sxs-lookup"><span data-stu-id="420a8-320">It serializes them as JSON strings.</span></span>
* <span data-ttu-id="420a8-321">它在反序列化期间接受 JSON 数字和括在引号中的数字。</span><span class="sxs-lookup"><span data-stu-id="420a8-321">It accepts JSON numbers and numbers within quotes while deserializing.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/LongToStringConverter.cs)]

<span data-ttu-id="420a8-322">通过对各个 `long` 属性[使用特性](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property)或是通过向 [ 集合](system-text-json-converters-how-to.md#registration-sample---converters-collection)添加转换器<xref:System.Text.Json.JsonSerializerOptions.Converters>来注册此自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="420a8-322">Register this custom converter by [using an attribute](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) on individual `long` properties or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

### <a name="dictionary-with-non-string-key"></a><span data-ttu-id="420a8-323">包含非字符串键的字典</span><span class="sxs-lookup"><span data-stu-id="420a8-323">Dictionary with non-string key</span></span>

<span data-ttu-id="420a8-324">`Newtonsoft.Json` 支持类型 `Dictionary<TKey, TValue>` 的集合。</span><span class="sxs-lookup"><span data-stu-id="420a8-324">`Newtonsoft.Json` supports collections of type `Dictionary<TKey, TValue>`.</span></span> <span data-ttu-id="420a8-325"><xref:System.Text.Json> 中对字典集合的内置支持仅限于 `Dictionary<string, TValue>`。</span><span class="sxs-lookup"><span data-stu-id="420a8-325">The built-in support for dictionary collections in <xref:System.Text.Json> is limited to `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="420a8-326">即，键必须是字符串。</span><span class="sxs-lookup"><span data-stu-id="420a8-326">That is, the key must be a string.</span></span>

<span data-ttu-id="420a8-327">若要支持将整数或某种其他类型用作键的字典，请创建转换器（类似于[如何编写自定义转换器](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key)中的示例）。</span><span class="sxs-lookup"><span data-stu-id="420a8-327">To support a dictionary with an integer or some other type as the key, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).</span></span>

### <a name="polymorphic-serialization"></a><span data-ttu-id="420a8-328">多态序列化</span><span class="sxs-lookup"><span data-stu-id="420a8-328">Polymorphic serialization</span></span>

<span data-ttu-id="420a8-329">`Newtonsoft.Json` 会自动执行多态序列化。</span><span class="sxs-lookup"><span data-stu-id="420a8-329">`Newtonsoft.Json` automatically does polymorphic serialization.</span></span> <span data-ttu-id="420a8-330">有关 <xref:System.Text.Json> 的有限多态序列化功能的信息，请参阅[序列化派生类的属性](system-text-json-how-to.md#serialize-properties-of-derived-classes)。</span><span class="sxs-lookup"><span data-stu-id="420a8-330">For information about the limited polymorphic serialization capabilities of <xref:System.Text.Json>, see [Serialize properties of derived classes](system-text-json-how-to.md#serialize-properties-of-derived-classes).</span></span>

<span data-ttu-id="420a8-331">所述的解决方法是定义可能以类型 `object` 的形式包含派生类的属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-331">The workaround described there is to define properties that may contain derived classes as type `object`.</span></span> <span data-ttu-id="420a8-332">如果无法这样，则另一种选择是为整个继承类型层次结构创建带有 `Write` 方法的转换器（类似于[如何编写自定义转换器](system-text-json-converters-how-to.md#support-polymorphic-deserialization)中的示例）。</span><span class="sxs-lookup"><span data-stu-id="420a8-332">If that isn't possible, another option is to create a converter with a `Write` method for the whole inheritance type hierarchy like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

### <a name="polymorphic-deserialization"></a><span data-ttu-id="420a8-333">多态反序列化</span><span class="sxs-lookup"><span data-stu-id="420a8-333">Polymorphic deserialization</span></span>

<span data-ttu-id="420a8-334">`Newtonsoft.Json` 具有 `TypeNameHandling` 设置，它在序列化期间将类型名称元数据添加到 JSON。</span><span class="sxs-lookup"><span data-stu-id="420a8-334">`Newtonsoft.Json` has a `TypeNameHandling` setting that adds type name metadata to the JSON while serializing.</span></span> <span data-ttu-id="420a8-335">它在反序列化期间使用元数据执行多态反序列化。</span><span class="sxs-lookup"><span data-stu-id="420a8-335">It uses the metadata while deserializing to do polymorphic deserialization.</span></span> <span data-ttu-id="420a8-336"><xref:System.Text.Json> 可以执行有限范围的[多态序列化](system-text-json-how-to.md#serialize-properties-of-derived-classes)，但不能执行多态反序列化。</span><span class="sxs-lookup"><span data-stu-id="420a8-336"><xref:System.Text.Json> can do a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but not polymorphic deserialization.</span></span>

<span data-ttu-id="420a8-337">若要支持多态反序列化，请创建转换器（类似于[如何编写自定义转换器](system-text-json-converters-how-to.md#support-polymorphic-deserialization)中的示例）。</span><span class="sxs-lookup"><span data-stu-id="420a8-337">To support polymorphic deserialization, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

### <a name="deserialization-of-object-properties"></a><span data-ttu-id="420a8-338">对象属性的反序列化</span><span class="sxs-lookup"><span data-stu-id="420a8-338">Deserialization of object properties</span></span>

<span data-ttu-id="420a8-339">当 `Newtonsoft.Json` 反序列化为 <xref:System.Object> 时，它会：</span><span class="sxs-lookup"><span data-stu-id="420a8-339">When `Newtonsoft.Json` deserializes to <xref:System.Object>, it:</span></span>

* <span data-ttu-id="420a8-340">推断 JSON 有效负载中的基元值的类型（不是 `null`），并以装箱对象的形式返回存储的 `string`、`long`、`double`、`boolean` 或 `DateTime`。</span><span class="sxs-lookup"><span data-stu-id="420a8-340">Infers the type of primitive values in the JSON payload (other than `null`) and returns the stored `string`, `long`, `double`, `boolean`, or `DateTime` as a boxed object.</span></span> <span data-ttu-id="420a8-341">基元值是单个 JSON 值，如 JSON 数字、字符串、`true`、`false` 或 `null`。</span><span class="sxs-lookup"><span data-stu-id="420a8-341">*Primitive values* are single JSON values such as a JSON number, string, `true`, `false`, or `null`.</span></span>
* <span data-ttu-id="420a8-342">为 JSON 有效负载中的复杂值返回 `JObject` 或 `JArray`。</span><span class="sxs-lookup"><span data-stu-id="420a8-342">Returns a `JObject` or `JArray` for complex values in the JSON payload.</span></span> <span data-ttu-id="420a8-343">复杂值是括在大括号 (`{}`) 中的 JSON 键值对的集合或括在方括号 (`[]`) 中的值的列表。</span><span class="sxs-lookup"><span data-stu-id="420a8-343">*Complex values* are collections of JSON key-value pairs within braces (`{}`) or lists of values within brackets (`[]`).</span></span> <span data-ttu-id="420a8-344">括在大括号或方括号中的属性和值可以具有附加属性或值。</span><span class="sxs-lookup"><span data-stu-id="420a8-344">The properties and values within the braces or brackets can have additional properties or values.</span></span>
* <span data-ttu-id="420a8-345">当有效负载具有 `null` JSON 文本时，返回空引用。</span><span class="sxs-lookup"><span data-stu-id="420a8-345">Returns a null reference when the payload has the `null` JSON literal.</span></span>

<span data-ttu-id="420a8-346"><xref:System.Text.Json> 在每次反序列化为 <xref:System.Object> 时，为基元和复数值存储装箱 `JsonElement`，例如：</span><span class="sxs-lookup"><span data-stu-id="420a8-346"><xref:System.Text.Json> stores a boxed `JsonElement` for both primitive and complex values whenever deserializing to <xref:System.Object>, for example:</span></span>

* <span data-ttu-id="420a8-347">`object` 属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-347">An `object` property.</span></span>
* <span data-ttu-id="420a8-348">`object` 字典值。</span><span class="sxs-lookup"><span data-stu-id="420a8-348">An `object` dictionary value.</span></span>
* <span data-ttu-id="420a8-349">`object` 数组值。</span><span class="sxs-lookup"><span data-stu-id="420a8-349">An `object` array value.</span></span>
* <span data-ttu-id="420a8-350">根 `object`。</span><span class="sxs-lookup"><span data-stu-id="420a8-350">A root `object`.</span></span>

<span data-ttu-id="420a8-351">但是，`System.Text.Json` 处理 `null` 的方式与 `Newtonsoft.Json` 相同，会在有效负载中包含 `null` JSON 文本时返回空引用。</span><span class="sxs-lookup"><span data-stu-id="420a8-351">However, `System.Text.Json` treats `null` the same as `Newtonsoft.Json` and returns a null reference when the payload has the `null` JSON literal in it.</span></span>

<span data-ttu-id="420a8-352">若要为 `object` 实现类型推理，请创建转换器（类似于[如何编写自定义转换器](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties)中的示例）。</span><span class="sxs-lookup"><span data-stu-id="420a8-352">To implement type inference for `object` properties, create a converter like the example in [How to write custom converters](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).</span></span>

### <a name="deserialize-null-to-non-nullable-type"></a><span data-ttu-id="420a8-353">将 null 反序列化为不可为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="420a8-353">Deserialize null to non-nullable type</span></span>

<span data-ttu-id="420a8-354">`Newtonsoft.Json` 在以下方案中不会引发异常：</span><span class="sxs-lookup"><span data-stu-id="420a8-354">`Newtonsoft.Json` doesn't throw an exception in the following scenario:</span></span>

* <span data-ttu-id="420a8-355">`NullValueHandling` 设置为 `Ignore`，并且</span><span class="sxs-lookup"><span data-stu-id="420a8-355">`NullValueHandling` is set to `Ignore`, and</span></span>
* <span data-ttu-id="420a8-356">在反序列化过程中，JSON 对于不可为 null 的值类型包含 null 值。</span><span class="sxs-lookup"><span data-stu-id="420a8-356">During deserialization, the JSON contains a null value for a non-nullable value type.</span></span>

<span data-ttu-id="420a8-357">在相同方案中，<xref:System.Text.Json> 会引发异常。</span><span class="sxs-lookup"><span data-stu-id="420a8-357">In the same scenario, <xref:System.Text.Json> does throw an exception.</span></span> <span data-ttu-id="420a8-358">（对应的 null 处理设置为 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>。）</span><span class="sxs-lookup"><span data-stu-id="420a8-358">(The corresponding null handling setting is <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>.)</span></span>

<span data-ttu-id="420a8-359">如果你拥有目标类型，在最佳解决方法是使相关属性可为 null（例如，将 `int` 更改为 `int?`）。</span><span class="sxs-lookup"><span data-stu-id="420a8-359">If you own the target type, the best workaround is to make the property in question nullable (for example, change `int` to `int?`).</span></span>

<span data-ttu-id="420a8-360">另一种解决方法是为类型创建转换器，如以下为 `DateTimeOffset` 类型处理 null 值的示例：</span><span class="sxs-lookup"><span data-stu-id="420a8-360">Another workaround is to make a converter for the type, such as the following example that handles null values for `DateTimeOffset` types:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DateTimeOffsetNullHandlingConverter.cs)]

<span data-ttu-id="420a8-361">通过[对属性使用特性](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property)或是通过向 <xref:System.Text.Json.JsonSerializerOptions.Converters> 集合[添加转换器](system-text-json-converters-how-to.md#registration-sample---converters-collection)来注册此自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="420a8-361">Register this custom converter by [using an attribute on the property](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="420a8-362">**注意：** 前面的转换器处理 null 值的方式与 `Newtonsoft.Json` 为指定默认值的 POCO 进行处理的方式不同。</span><span class="sxs-lookup"><span data-stu-id="420a8-362">**Note:** The preceding converter **handles null values differently** than `Newtonsoft.Json` does for POCOs that specify default values.</span></span> <span data-ttu-id="420a8-363">例如，假设以下代码表示目标对象：</span><span class="sxs-lookup"><span data-stu-id="420a8-363">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="420a8-364">并且假设使用前面的转换器反序列化以下 JSON：</span><span class="sxs-lookup"><span data-stu-id="420a8-364">And suppose the following JSON is deserialized by using the preceding converter:</span></span>

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="420a8-365">反序列化之后，`Date` 属性具有 1/1/0001 (`default(DateTimeOffset)`)，即，在构造函数中设置的值会被覆盖。</span><span class="sxs-lookup"><span data-stu-id="420a8-365">After deserialization, the `Date` property has 1/1/0001 (`default(DateTimeOffset)`), that is, the value set in the constructor is overwritten.</span></span> <span data-ttu-id="420a8-366">给定相同 POCO 和 JSON，`Newtonsoft.Json` 反序列化会将 1/1/2001 保留在 `Date` 属性中。</span><span class="sxs-lookup"><span data-stu-id="420a8-366">Given the same POCO and JSON, `Newtonsoft.Json` deserialization would leave 1/1/2001 in the `Date` property.</span></span>

### <a name="deserialize-to-immutable-classes-and-structs"></a><span data-ttu-id="420a8-367">反序列化为不可变类和结构</span><span class="sxs-lookup"><span data-stu-id="420a8-367">Deserialize to immutable classes and structs</span></span>

<span data-ttu-id="420a8-368">`Newtonsoft.Json` 可以反序列化为不可变类和结构，因为它可以使用具有参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="420a8-368">`Newtonsoft.Json` can deserialize to immutable classes and structs because it can use constructors that have parameters.</span></span> <span data-ttu-id="420a8-369"><xref:System.Text.Json> 仅支持公共无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="420a8-369"><xref:System.Text.Json> supports only public parameterless constructors.</span></span> <span data-ttu-id="420a8-370">作为一种解决方法，可以在自定义转换器中调用具有参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="420a8-370">As a workaround, you can call a constructor with parameters in a custom converter.</span></span>

<span data-ttu-id="420a8-371">下面是具有多个构造函数参数的不可变结构：</span><span class="sxs-lookup"><span data-stu-id="420a8-371">Here's an immutable struct with multiple constructor parameters:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/ImmutablePoint.cs#ImmutablePoint)]

<span data-ttu-id="420a8-372">下面是序列化和反序列化此结构的转换器：</span><span class="sxs-lookup"><span data-stu-id="420a8-372">And here's a converter that serializes and deserializes this struct:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/ImmutablePointConverter.cs)]

<span data-ttu-id="420a8-373">通过向 <xref:System.Text.Json.JsonSerializerOptions.Converters> 集合[添加转换器](system-text-json-converters-how-to.md#registration-sample---converters-collection)来注册此自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="420a8-373">Register this custom converter by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="420a8-374">有关处理开放式泛型属性的类似转换器的示例，请参阅[用于键/值对的内置转换器](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs)。</span><span class="sxs-lookup"><span data-stu-id="420a8-374">For an example of a similar converter that handles open generic properties, see the [built-in converter for key-value pairs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs).</span></span>

### <a name="specify-constructor-to-use"></a><span data-ttu-id="420a8-375">指定要使用的构造函数</span><span class="sxs-lookup"><span data-stu-id="420a8-375">Specify constructor to use</span></span>

<span data-ttu-id="420a8-376">使用 `Newtonsoft.Json` `[JsonConstructor]` 特性可以指定在反序列化为 POCO 时要调用的构造函数。</span><span class="sxs-lookup"><span data-stu-id="420a8-376">The `Newtonsoft.Json` `[JsonConstructor]` attribute lets you specify which constructor to call when deserializing to a POCO.</span></span> <span data-ttu-id="420a8-377"><xref:System.Text.Json> 仅支持无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="420a8-377"><xref:System.Text.Json> supports only parameterless constructors.</span></span> <span data-ttu-id="420a8-378">作为一种解决方法，可以在自定义转换器中调用所需的任何构造函数。</span><span class="sxs-lookup"><span data-stu-id="420a8-378">As a workaround, you can call whichever constructor you need in a custom converter.</span></span> <span data-ttu-id="420a8-379">请参阅[反序列化为不可变类和结构](#deserialize-to-immutable-classes-and-structs)的示例。</span><span class="sxs-lookup"><span data-stu-id="420a8-379">See the example for [Deserialize to immutable classes and structs](#deserialize-to-immutable-classes-and-structs).</span></span>

### <a name="required-properties"></a><span data-ttu-id="420a8-380">必需的属性</span><span class="sxs-lookup"><span data-stu-id="420a8-380">Required properties</span></span>

<span data-ttu-id="420a8-381">在 `Newtonsoft.Json` 中，通过对 `[JsonProperty]` 特性设置 `Required` 来指定属性是必需的。</span><span class="sxs-lookup"><span data-stu-id="420a8-381">In `Newtonsoft.Json`, you specify that a property is required by setting `Required` on the `[JsonProperty]` attribute.</span></span> <span data-ttu-id="420a8-382">如果在 JSON 中没有为标记为必需的属性收到值，`Newtonsoft.Json` 会引发异常。</span><span class="sxs-lookup"><span data-stu-id="420a8-382">`Newtonsoft.Json` throws an exception if no value is received in the JSON for a property marked as required.</span></span>

<span data-ttu-id="420a8-383">如果没有为目标类型的某个属性收到值，<xref:System.Text.Json> 不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="420a8-383"><xref:System.Text.Json> doesn't throw an exception if no value is received for one of the properties of the target type.</span></span> <span data-ttu-id="420a8-384">例如，如果具有 `WeatherForecast` 类：</span><span class="sxs-lookup"><span data-stu-id="420a8-384">For example, if you have a `WeatherForecast` class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="420a8-385">以下 JSON 可反序列化，不会发生错误：</span><span class="sxs-lookup"><span data-stu-id="420a8-385">The following JSON is deserialized without error:</span></span>

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

<span data-ttu-id="420a8-386">若要使反序列化在 JSON 中没有 `Date` 属性时失败，请实现自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="420a8-386">To make deserialization fail if no `Date` property is in the JSON, implement a custom converter.</span></span> <span data-ttu-id="420a8-387">如果反序列化完成之后未设置 `Date` 属性，则以下示例转换器代码会引发异常：</span><span class="sxs-lookup"><span data-stu-id="420a8-387">The following sample converter code throws an exception if the `Date` property isn't set after deserialization is complete:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastRequiredPropertyConverter.cs)]

<span data-ttu-id="420a8-388">通过[对 POCO 类使用特性](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type)或是通过向 <xref:System.Text.Json.JsonSerializerOptions.Converters> 集合[添加转换器](system-text-json-converters-how-to.md#registration-sample---converters-collection)来注册此自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="420a8-388">Register this custom converter by [using an attribute on the POCO class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="420a8-389">如果遵循此模式，请不要在递归调用 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 或 <xref:System.Text.Json.JsonSerializer.Deserialize%2A> 时传入选项对象。</span><span class="sxs-lookup"><span data-stu-id="420a8-389">If you follow this pattern, don't pass in the options object when recursively calling <xref:System.Text.Json.JsonSerializer.Serialize%2A> or <xref:System.Text.Json.JsonSerializer.Deserialize%2A>.</span></span> <span data-ttu-id="420a8-390">选项对象包含 <xref:System.Text.Json.JsonSerializerOptions.Converters%2A> 集合。</span><span class="sxs-lookup"><span data-stu-id="420a8-390">The options object contains the <xref:System.Text.Json.JsonSerializerOptions.Converters%2A> collection.</span></span> <span data-ttu-id="420a8-391">如果将它传递给 `Serialize` 或 `Deserialize`，则自定义转换器会调入其自身，从而产生导致堆栈溢出异常的无限循环。</span><span class="sxs-lookup"><span data-stu-id="420a8-391">If you pass it in to `Serialize` or `Deserialize`, the custom converter calls into itself, making an infinite loop that results in a stack overflow exception.</span></span> <span data-ttu-id="420a8-392">如果默认选项不可行，请使用所需设置创建选项的新实例。</span><span class="sxs-lookup"><span data-stu-id="420a8-392">If the default options are not feasible, create a new instance of the options with the settings that you need.</span></span> <span data-ttu-id="420a8-393">此方法会速度较慢，因为每个新实例都会独立缓存。</span><span class="sxs-lookup"><span data-stu-id="420a8-393">This approach will be slow since each new instance caches independently.</span></span>

<span data-ttu-id="420a8-394">前面的转换器代码是简化示例。</span><span class="sxs-lookup"><span data-stu-id="420a8-394">The preceding converter code is a simplified example.</span></span> <span data-ttu-id="420a8-395">如果需要处理特性（例如 [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute)）或不同选项（如自定义编码器），则需要其他逻辑。</span><span class="sxs-lookup"><span data-stu-id="420a8-395">Additional logic would be required if you need to handle attributes (such as [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) or different options (such as custom encoders).</span></span> <span data-ttu-id="420a8-396">此外，示例代码不处理在构造函数中为其设置了默认值的属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-396">Also, the example code doesn't handle properties for which a default value is set in the constructor.</span></span> <span data-ttu-id="420a8-397">而且此方法不区分以下情况：</span><span class="sxs-lookup"><span data-stu-id="420a8-397">And this approach doesn't differentiate between the following scenarios:</span></span>

* <span data-ttu-id="420a8-398">JSON 中缺少属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-398">A property is missing from the JSON.</span></span>
* <span data-ttu-id="420a8-399">JSON 中存在不可为 null 的类型的属性，但值是该类型的默认值，如 `int` 的值为零。</span><span class="sxs-lookup"><span data-stu-id="420a8-399">A property for a non-nullable type is present in the JSON, but the value is the default for the type, such as zero for an `int`.</span></span>
* <span data-ttu-id="420a8-400">JSON 中存在可为 null 的值类型的属性，但值为 null。</span><span class="sxs-lookup"><span data-stu-id="420a8-400">A property for a nullable value type is present in the JSON, but the value is null.</span></span>

### <a name="conditionally-ignore-a-property"></a><span data-ttu-id="420a8-401">有条件地忽略属性</span><span class="sxs-lookup"><span data-stu-id="420a8-401">Conditionally ignore a property</span></span>

<span data-ttu-id="420a8-402">`Newtonsoft.Json` 有多种方法可在序列化或反序列化时有条件地忽略属性：</span><span class="sxs-lookup"><span data-stu-id="420a8-402">`Newtonsoft.Json` has several ways to conditionally ignore a property on serialization or deserialization:</span></span>

* <span data-ttu-id="420a8-403">`DefaultContractResolver` 使你可以基于任意条件选择要包含或排除的属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-403">`DefaultContractResolver` lets you select properties to include or exclude, based on arbitrary criteria.</span></span>
* <span data-ttu-id="420a8-404">`JsonSerializerSettings` 上的 `NullValueHandling` 和 `DefaultValueHandling` 设置使你指定应忽略所有 null 值或默认值属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-404">The `NullValueHandling` and `DefaultValueHandling` settings on `JsonSerializerSettings` let you specify that all null-value or default-value properties should be ignored.</span></span>
* <span data-ttu-id="420a8-405">`[JsonProperty]` 特性上的 `NullValueHandling` 和 `DefaultValueHandling` 设置使你可以指定在设置为 null 或默认值时应忽略的单个属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-405">The `NullValueHandling` and `DefaultValueHandling` settings on the `[JsonProperty]` attribute let you specify individual properties that should be ignored when set to null or the default value.</span></span>

<span data-ttu-id="420a8-406"><xref:System.Text.Json> 提供以下方法，用于在序列化期间省略属性：</span><span class="sxs-lookup"><span data-stu-id="420a8-406"><xref:System.Text.Json> provides the following ways to omit properties while serializing:</span></span>

* <span data-ttu-id="420a8-407">属性上的 [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties) 特性会导致在序列化过程中从 JSON 中省略属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-407">The [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties) attribute on a property causes the property to be omitted from the JSON during serialization.</span></span>
* <span data-ttu-id="420a8-408">[IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) 全局选项使你可以排除所有 null 值属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-408">The [IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) global option lets you exclude all null-value properties.</span></span>
* <span data-ttu-id="420a8-409">[IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) 全局选项使你可以排除所有只读属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-409">The [IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) global option lets you exclude all read-only properties.</span></span>

<span data-ttu-id="420a8-410">不能通过这些选项：</span><span class="sxs-lookup"><span data-stu-id="420a8-410">These options **don't** let you:</span></span>

* <span data-ttu-id="420a8-411">忽略具有类型的默认值的所有属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-411">Ignore all properties that have the default value for the type.</span></span>
* <span data-ttu-id="420a8-412">忽略具有类型的默认值的所选属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-412">Ignore selected properties that have the default value for the type.</span></span>
* <span data-ttu-id="420a8-413">忽略值为 null 的所选属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-413">Ignore selected properties if their value is null.</span></span>
* <span data-ttu-id="420a8-414">基于运行时计算的任意条件忽略所选属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-414">Ignore selected properties based on arbitrary criteria evaluated at run time.</span></span>

<span data-ttu-id="420a8-415">对于该功能，可以编写自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="420a8-415">For that functionality, you can write a custom converter.</span></span> <span data-ttu-id="420a8-416">下面是一个示例 POCO 和一个适用于它的自定义转换器，用于说明此方法：</span><span class="sxs-lookup"><span data-stu-id="420a8-416">Here's a sample POCO and a custom converter for it that illustrates this approach:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

<span data-ttu-id="420a8-417">如果值为 null、空字符串或 "N/A"，则转换器会导致从序列化中省略 `Summary` 属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-417">The converter causes the `Summary` property to be omitted from serialization if its value is null, an empty string, or "N/A".</span></span>

<span data-ttu-id="420a8-418">通过[对类使用特性](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type)或是通过向 <xref:System.Text.Json.JsonSerializerOptions.Converters> 集合[添加转换器](system-text-json-converters-how-to.md#registration-sample---converters-collection)来注册此自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="420a8-418">Register this custom converter by [using an attribute on the class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="420a8-419">此方法在以下情况下需要其他逻辑：</span><span class="sxs-lookup"><span data-stu-id="420a8-419">This approach requires additional logic if:</span></span>

* <span data-ttu-id="420a8-420">POCO 包含复杂属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-420">The POCO includes complex properties.</span></span>
* <span data-ttu-id="420a8-421">需要处理特性（如 `[JsonIgnore]`）或选项（如自定义编码器）。</span><span class="sxs-lookup"><span data-stu-id="420a8-421">You need to handle attributes such as `[JsonIgnore]` or options such as custom encoders.</span></span>

### <a name="specify-date-format"></a><span data-ttu-id="420a8-422">指定日期格式</span><span class="sxs-lookup"><span data-stu-id="420a8-422">Specify date format</span></span>

<span data-ttu-id="420a8-423">`Newtonsoft.Json` 提供多种方法来控制如何序列化和反序列化 `DateTime` 和 `DateTimeOffset` 类型的属性：</span><span class="sxs-lookup"><span data-stu-id="420a8-423">`Newtonsoft.Json` provides several ways to control how properties of `DateTime` and `DateTimeOffset` types are serialized and deserialized:</span></span>

* <span data-ttu-id="420a8-424">`DateTimeZoneHandling` 设置可用于将所有 `DateTime` 值序列化为 UTC 日期。</span><span class="sxs-lookup"><span data-stu-id="420a8-424">The `DateTimeZoneHandling` setting can be used to serialize all `DateTime` values as UTC dates.</span></span>
* <span data-ttu-id="420a8-425">`DateFormatString` 设置和 `DateTime` 转换器可用于自定义日期字符串的格式。</span><span class="sxs-lookup"><span data-stu-id="420a8-425">The `DateFormatString` setting and `DateTime` converters can be used to customize the format of date strings.</span></span>

<span data-ttu-id="420a8-426">在 <xref:System.Text.Json> 中，具有内置支持的唯一格式是 ISO 8601-1:2019，因为它被广泛采用、意义明确并且可精确地进行往返。</span><span class="sxs-lookup"><span data-stu-id="420a8-426">In <xref:System.Text.Json>, the only format that has built-in support is ISO 8601-1:2019 since it's widely adopted, unambiguous, and makes round trips precisely.</span></span> <span data-ttu-id="420a8-427">若要使用任何其他格式，请创建自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="420a8-427">To use any other format, create a custom converter.</span></span> <span data-ttu-id="420a8-428">有关详细信息，请参阅 [System.Text.Json 中的 DateTime 和 DateTimeOffset 支持](../datetime/system-text-json-support.md)。</span><span class="sxs-lookup"><span data-stu-id="420a8-428">For more information, see [DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md).</span></span>

### <a name="callbacks"></a><span data-ttu-id="420a8-429">回调</span><span class="sxs-lookup"><span data-stu-id="420a8-429">Callbacks</span></span>

<span data-ttu-id="420a8-430">`Newtonsoft.Json` 使你可以在序列化或反序列化过程中的多个点执行自定义代码：</span><span class="sxs-lookup"><span data-stu-id="420a8-430">`Newtonsoft.Json` lets you execute custom code at several points in the serialization or deserialization process:</span></span>

* <span data-ttu-id="420a8-431">OnDeserializing（开始反序列化对象时）</span><span class="sxs-lookup"><span data-stu-id="420a8-431">OnDeserializing (when beginning to deserialize an object)</span></span>
* <span data-ttu-id="420a8-432">OnDeserialized（对象反序列化完成时）</span><span class="sxs-lookup"><span data-stu-id="420a8-432">OnDeserialized (when finished deserializing an object)</span></span>
* <span data-ttu-id="420a8-433">OnSerializing（开始序列化对象时）</span><span class="sxs-lookup"><span data-stu-id="420a8-433">OnSerializing (when beginning to serialize an object)</span></span>
* <span data-ttu-id="420a8-434">OnSerialized（对象序列化完成时）</span><span class="sxs-lookup"><span data-stu-id="420a8-434">OnSerialized (when finished serializing an object)</span></span>

<span data-ttu-id="420a8-435">在 <xref:System.Text.Json> 中，可以通过编写自定义转换器来模拟回调。</span><span class="sxs-lookup"><span data-stu-id="420a8-435">In <xref:System.Text.Json>, you can simulate callbacks by writing a custom converter.</span></span> <span data-ttu-id="420a8-436">以下示例演示适用于 POCO 的自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="420a8-436">The following example shows a custom converter for a POCO.</span></span> <span data-ttu-id="420a8-437">该转换器包含在与 `Newtonsoft.Json` 回调相对应的每个点显示消息的代码。</span><span class="sxs-lookup"><span data-stu-id="420a8-437">The converter includes code that displays a message at each point that corresponds to a `Newtonsoft.Json` callback.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastCallbacksConverter.cs)]

<span data-ttu-id="420a8-438">通过[对类使用特性](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type)或是通过向 <xref:System.Text.Json.JsonSerializerOptions.Converters> 集合[添加转换器](system-text-json-converters-how-to.md#registration-sample---converters-collection)来注册此自定义转换器。</span><span class="sxs-lookup"><span data-stu-id="420a8-438">Register this custom converter by [using an attribute on the class](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) or by [adding the converter](system-text-json-converters-how-to.md#registration-sample---converters-collection) to the <xref:System.Text.Json.JsonSerializerOptions.Converters> collection.</span></span>

<span data-ttu-id="420a8-439">如果使用遵循前面示例的自定义转换器：</span><span class="sxs-lookup"><span data-stu-id="420a8-439">If you use a custom converter that follows the preceding sample:</span></span>

* <span data-ttu-id="420a8-440">`OnDeserializing` 代码无权访问新 POCO 实例。</span><span class="sxs-lookup"><span data-stu-id="420a8-440">The `OnDeserializing` code doesn't have access to the new POCO instance.</span></span> <span data-ttu-id="420a8-441">若要在反序列化开始时操作新 POCO 实例，请将该代码放入 POCO 构造函数中。</span><span class="sxs-lookup"><span data-stu-id="420a8-441">To manipulate the new POCO instance at the start of deserialization, put that code in the POCO constructor.</span></span>
* <span data-ttu-id="420a8-442">当递归调用 `Serialize` 或 `Deserialize` 时，请不要传入选项对象。</span><span class="sxs-lookup"><span data-stu-id="420a8-442">Don't pass in the options object when recursively calling `Serialize` or `Deserialize`.</span></span> <span data-ttu-id="420a8-443">选项对象包含 `Converters` 集合。</span><span class="sxs-lookup"><span data-stu-id="420a8-443">The options object contains the `Converters` collection.</span></span> <span data-ttu-id="420a8-444">如果将它传递给 `Serialize` 或 `Deserialize`，则会使用转换器，从而产生导致堆栈溢出异常的无限循环。</span><span class="sxs-lookup"><span data-stu-id="420a8-444">If you pass it in to `Serialize` or `Deserialize`, the converter will be used, making an infinite loop that results in a stack overflow exception.</span></span>

### <a name="public-and-non-public-fields"></a><span data-ttu-id="420a8-445">公共和非公共字段</span><span class="sxs-lookup"><span data-stu-id="420a8-445">Public and non-public fields</span></span>

<span data-ttu-id="420a8-446">`Newtonsoft.Json` 可以序列化和反序列化字段以及属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-446">`Newtonsoft.Json` can serialize and deserialize fields as well as properties.</span></span> <span data-ttu-id="420a8-447"><xref:System.Text.Json> 仅适用于公共属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-447"><xref:System.Text.Json> only works with public properties.</span></span> <span data-ttu-id="420a8-448">自定义转换器可提供此功能。</span><span class="sxs-lookup"><span data-stu-id="420a8-448">Custom converters can provide this functionality.</span></span>

### <a name="internal-and-private-property-setters-and-getters"></a><span data-ttu-id="420a8-449">内部和私有属性 setter 和 getter</span><span class="sxs-lookup"><span data-stu-id="420a8-449">Internal and private property setters and getters</span></span>

<span data-ttu-id="420a8-450">`Newtonsoft.Json` 可以通过 `JsonProperty` 特性使用私有和内部属性 setter 和 getter。</span><span class="sxs-lookup"><span data-stu-id="420a8-450">`Newtonsoft.Json` can use private and internal property setters and getters via the `JsonProperty` attribute.</span></span> <span data-ttu-id="420a8-451"><xref:System.Text.Json> 仅支持公共 setter。</span><span class="sxs-lookup"><span data-stu-id="420a8-451"><xref:System.Text.Json> supports only public setters.</span></span> <span data-ttu-id="420a8-452">自定义转换器可提供此功能。</span><span class="sxs-lookup"><span data-stu-id="420a8-452">Custom converters can provide this functionality.</span></span>

### <a name="populate-existing-objects"></a><span data-ttu-id="420a8-453">填充现有对象</span><span class="sxs-lookup"><span data-stu-id="420a8-453">Populate existing objects</span></span>

<span data-ttu-id="420a8-454">`Newtonsoft.Json` 中的 `JsonConvert.PopulateObject` 方法将 JSON 文档反序列化为类的现有实例，而不是创建新实例。</span><span class="sxs-lookup"><span data-stu-id="420a8-454">The `JsonConvert.PopulateObject` method in `Newtonsoft.Json` deserializes a JSON document to an existing instance of a class, instead of creating a new instance.</span></span> <span data-ttu-id="420a8-455"><xref:System.Text.Json> 始终使用默认公共无参数构造函数创建目标类型的新实例。</span><span class="sxs-lookup"><span data-stu-id="420a8-455"><xref:System.Text.Json> always creates a new instance of the target type by using the default public parameterless constructor.</span></span> <span data-ttu-id="420a8-456">自定义转换器可以反序列化为现有实例。</span><span class="sxs-lookup"><span data-stu-id="420a8-456">Custom converters can deserialize to an existing instance.</span></span>

### <a name="reuse-rather-than-replace-properties"></a><span data-ttu-id="420a8-457">重用而不是替换属性</span><span class="sxs-lookup"><span data-stu-id="420a8-457">Reuse rather than replace properties</span></span>

<span data-ttu-id="420a8-458">`Newtonsoft.Json` `ObjectCreationHandling` 设置使你可以指定在反序列化过程中应重用属性中的对象，而不是进行替换。</span><span class="sxs-lookup"><span data-stu-id="420a8-458">The `Newtonsoft.Json` `ObjectCreationHandling` setting lets you specify that objects in properties should be reused rather than replaced during deserialization.</span></span> <span data-ttu-id="420a8-459"><xref:System.Text.Json> 始终替换属性中的对象。</span><span class="sxs-lookup"><span data-stu-id="420a8-459"><xref:System.Text.Json> always replaces objects in properties.</span></span>  <span data-ttu-id="420a8-460">自定义转换器可提供此功能。</span><span class="sxs-lookup"><span data-stu-id="420a8-460">Custom converters can provide this functionality.</span></span>

### <a name="add-to-collections-without-setters"></a><span data-ttu-id="420a8-461">在不带 setter 的情况下添加到集合</span><span class="sxs-lookup"><span data-stu-id="420a8-461">Add to collections without setters</span></span>

<span data-ttu-id="420a8-462">在反序列化过程中，`Newtonsoft.Json` 会将对象添加到集合，即使属性没有 setter。</span><span class="sxs-lookup"><span data-stu-id="420a8-462">During deserialization, `Newtonsoft.Json` adds objects to a collection even if the property has no setter.</span></span> <span data-ttu-id="420a8-463"><xref:System.Text.Json> 会忽略没有 setter 的属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-463"><xref:System.Text.Json> ignores properties that don't have setters.</span></span> <span data-ttu-id="420a8-464">自定义转换器可提供此功能。</span><span class="sxs-lookup"><span data-stu-id="420a8-464">Custom converters can provide this functionality.</span></span>

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a><span data-ttu-id="420a8-465">JsonSerializer 当前不支持的方案</span><span class="sxs-lookup"><span data-stu-id="420a8-465">Scenarios that JsonSerializer currently doesn't support</span></span>

<span data-ttu-id="420a8-466">对于以下方案，解决方法不可行或无法提供。</span><span class="sxs-lookup"><span data-stu-id="420a8-466">For the following scenarios, workarounds are not practical or possible.</span></span> <span data-ttu-id="420a8-467">如果你依赖于这些 `Newtonsoft.Json` 功能，则无法在不进行重大更改的情况下进行迁移。</span><span class="sxs-lookup"><span data-stu-id="420a8-467">If you rely on these `Newtonsoft.Json` features, migration will not be possible without significant changes.</span></span>

### <a name="preserve-object-references-and-handle-loops"></a><span data-ttu-id="420a8-468">保留对象引用并处理循环</span><span class="sxs-lookup"><span data-stu-id="420a8-468">Preserve object references and handle loops</span></span>

<span data-ttu-id="420a8-469">默认情况下，`Newtonsoft.Json` 按值进行序列化。</span><span class="sxs-lookup"><span data-stu-id="420a8-469">By default, `Newtonsoft.Json` serializes by value.</span></span> <span data-ttu-id="420a8-470">例如，如果对象包含两个属性，而这些属性包含对同一个 `Person` 对象的引用，该 `Person` 对象属性的值会在 JSON 重复。</span><span class="sxs-lookup"><span data-stu-id="420a8-470">For example, if an object contains two properties that contain a reference to the same `Person` object, the values of that `Person` object's properties are duplicated in the JSON.</span></span>

<span data-ttu-id="420a8-471">`Newtonsoft.Json` 在 `JsonSerializerSettings` 上有一个 `PreserveReferencesHandling` 设置，可让你按引用进行序列化：</span><span class="sxs-lookup"><span data-stu-id="420a8-471">`Newtonsoft.Json` has a `PreserveReferencesHandling` setting on `JsonSerializerSettings` that lets you serialize by reference:</span></span>

* <span data-ttu-id="420a8-472">标识符元数据会添加到为第一个 `Person` 对象创建的 JSON。</span><span class="sxs-lookup"><span data-stu-id="420a8-472">An identifier metadata is added to the JSON created for the first `Person` object.</span></span>
* <span data-ttu-id="420a8-473">为第二个 `Person` 对象创建的 JSON 包含对该标识符（而不是属性值）的引用。</span><span class="sxs-lookup"><span data-stu-id="420a8-473">The JSON that is created for the second `Person` object contains a reference to that identifier instead of property values.</span></span>

<span data-ttu-id="420a8-474">`Newtonsoft.Json` 还具有一个 `ReferenceLoopHandling` 设置，使你可以忽略循环引用，而不是引发异常。</span><span class="sxs-lookup"><span data-stu-id="420a8-474">`Newtonsoft.Json` also has a `ReferenceLoopHandling` setting that lets you ignore circular references rather than throw an exception.</span></span>

<span data-ttu-id="420a8-475"><xref:System.Text.Json> 仅支持按值进行进行序列化，并对循环引用引发异常。</span><span class="sxs-lookup"><span data-stu-id="420a8-475"><xref:System.Text.Json> only supports serialization by value and throws an exception for circular references.</span></span>

### <a name="systemruntimeserialization-attributes"></a><span data-ttu-id="420a8-476">System.Runtime.Serialization 特性</span><span class="sxs-lookup"><span data-stu-id="420a8-476">System.Runtime.Serialization attributes</span></span>

<span data-ttu-id="420a8-477"><xref:System.Text.Json> 不支持 `System.Runtime.Serialization` 命名空间中的特性，如 `DataMemberAttribute` 和 `IgnoreDataMemberAttribute`。</span><span class="sxs-lookup"><span data-stu-id="420a8-477"><xref:System.Text.Json> doesn't support attributes from the `System.Runtime.Serialization` namespace, such as `DataMemberAttribute` and `IgnoreDataMemberAttribute`.</span></span>

### <a name="octal-numbers"></a><span data-ttu-id="420a8-478">八进制数字</span><span class="sxs-lookup"><span data-stu-id="420a8-478">Octal numbers</span></span>

<span data-ttu-id="420a8-479">`Newtonsoft.Json` 将带前导零的数字视为八进制数字。</span><span class="sxs-lookup"><span data-stu-id="420a8-479">`Newtonsoft.Json` treats numbers with a leading zero as octal numbers.</span></span> <span data-ttu-id="420a8-480"><xref:System.Text.Json> 不允许存在前导零，因为 [RFC 8259](https://tools.ietf.org/html/rfc8259) 规范不允许。</span><span class="sxs-lookup"><span data-stu-id="420a8-480"><xref:System.Text.Json> doesn't allow leading zeroes because the [RFC 8259](https://tools.ietf.org/html/rfc8259) specification doesn't allow them.</span></span>

### <a name="missingmemberhandling"></a><span data-ttu-id="420a8-481">MissingMemberHandling</span><span class="sxs-lookup"><span data-stu-id="420a8-481">MissingMemberHandling</span></span>

<span data-ttu-id="420a8-482">`Newtonsoft.Json` 可以配置为在 JSON 包含目标类型中缺少的属性时，在反序列化过程中引发异常。</span><span class="sxs-lookup"><span data-stu-id="420a8-482">`Newtonsoft.Json` can be configured to throw exceptions during deserialization if the JSON includes properties that are missing in the target type.</span></span> <span data-ttu-id="420a8-483"><xref:System.Text.Json> 会忽略 JSON 中的额外属性，但在使用 [[JsonExtensionData] 特性](system-text-json-how-to.md#handle-overflow-json)时除外。</span><span class="sxs-lookup"><span data-stu-id="420a8-483"><xref:System.Text.Json> ignores extra properties in the JSON, except when you use the [[JsonExtensionData] attribute](system-text-json-how-to.md#handle-overflow-json).</span></span> <span data-ttu-id="420a8-484">对于缺少成员功能，没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="420a8-484">There's no workaround for the missing member feature.</span></span>

### <a name="tracewriter"></a><span data-ttu-id="420a8-485">TraceWriter</span><span class="sxs-lookup"><span data-stu-id="420a8-485">TraceWriter</span></span>

<span data-ttu-id="420a8-486">`Newtonsoft.Json` 使你可以使用 `TraceWriter` 进行调试，以查看序列化或反序列化所生成的日志。</span><span class="sxs-lookup"><span data-stu-id="420a8-486">`Newtonsoft.Json` lets you debug by using a `TraceWriter` to view logs that are generated by serialization or deserialization.</span></span> <span data-ttu-id="420a8-487"><xref:System.Text.Json> 不执行日志记录。</span><span class="sxs-lookup"><span data-stu-id="420a8-487"><xref:System.Text.Json> doesn't do logging.</span></span>

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a><span data-ttu-id="420a8-488">与 JToken（如 JObject、JArray）相比的 JsonDocument 和 JsonElement</span><span class="sxs-lookup"><span data-stu-id="420a8-488">JsonDocument and JsonElement compared to JToken (like JObject, JArray)</span></span>

<span data-ttu-id="420a8-489"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> 提供从现有 JSON 有效负载分析和生成只读文档对象模型 (DOM) 的功能。</span><span class="sxs-lookup"><span data-stu-id="420a8-489"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to parse and build a **read-only** Document Object Model (DOM) from existing JSON payloads.</span></span> <span data-ttu-id="420a8-490">DOM 提供对 JSON 有效负载中的数据的随机访问。</span><span class="sxs-lookup"><span data-stu-id="420a8-490">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="420a8-491">可以通过 <xref:System.Text.Json.JsonElement> 类型访问构成有效负载的 JSON 元素。</span><span class="sxs-lookup"><span data-stu-id="420a8-491">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="420a8-492">`JsonElement` 类型提供用于将 JSON 文本转换为常见 .NET 类型的 API。</span><span class="sxs-lookup"><span data-stu-id="420a8-492">The `JsonElement` type provides APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="420a8-493">`JsonDocument` 公开了 <xref:System.Text.Json.JsonDocument.RootElement> 属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-493">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

### <a name="jsondocument-is-idisposable"></a><span data-ttu-id="420a8-494">JsonDocument 为 IDisposable</span><span class="sxs-lookup"><span data-stu-id="420a8-494">JsonDocument is IDisposable</span></span>

<span data-ttu-id="420a8-495">`JsonDocument` 将内存中的数据视图生成到共用缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="420a8-495">`JsonDocument` builds an in-memory view of the data into a pooled buffer.</span></span> <span data-ttu-id="420a8-496">因此，与 `Newtonsoft.Json` 中的 `JObject` 或 `JArray` 不同，`JsonDocument` 类型实现 `IDisposable` 并且需要在 using 块中使用。</span><span class="sxs-lookup"><span data-stu-id="420a8-496">Therefore, unlike `JObject` or `JArray` from `Newtonsoft.Json`, the `JsonDocument` type implements `IDisposable` and needs to be used inside a using block.</span></span>

<span data-ttu-id="420a8-497">如果要将生存期所有权和释放责任转移到调用方，则只需从 API 返回 `JsonDocument`。</span><span class="sxs-lookup"><span data-stu-id="420a8-497">Only return a `JsonDocument` from your API if you want to transfer lifetime ownership and dispose responsibility to the caller.</span></span> <span data-ttu-id="420a8-498">在大多数情况下，这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="420a8-498">In most scenarios, that isn't necessary.</span></span> <span data-ttu-id="420a8-499">如果调用方需要处理整个 JSON 文档，则返回 <xref:System.Text.Json.JsonDocument.RootElement%2A> 的 <xref:System.Text.Json.JsonElement.Clone%2A>，这是 <xref:System.Text.Json.JsonElement>。</span><span class="sxs-lookup"><span data-stu-id="420a8-499">If the caller needs to work with the entire JSON document, return the <xref:System.Text.Json.JsonElement.Clone%2A> of the <xref:System.Text.Json.JsonDocument.RootElement%2A>, which is a <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="420a8-500">如果调用方需要处理 JSON 文档中的特定元素，则返回该 <xref:System.Text.Json.JsonElement> 的 <xref:System.Text.Json.JsonElement.Clone%2A>。</span><span class="sxs-lookup"><span data-stu-id="420a8-500">If the caller needs to work with a particular element within the JSON document, return the <xref:System.Text.Json.JsonElement.Clone%2A> of that <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="420a8-501">如果在不进行 `Clone` 的情况下直接返回 `RootElement` 或子元素，则在释放拥有返回的 `JsonElement` 的 `JsonDocument` 之后，调用方将无法访问它。</span><span class="sxs-lookup"><span data-stu-id="420a8-501">If you return the `RootElement` or a sub-element directly without making a `Clone`, the caller won't be able to access the returned `JsonElement` after the `JsonDocument` that owns it is disposed.</span></span>

<span data-ttu-id="420a8-502">下面是一个要求你进行 `Clone` 的示例：</span><span class="sxs-lookup"><span data-stu-id="420a8-502">Here's an example that requires you to make a `Clone`:</span></span>

```csharp
public JsonElement LookAndLoad(JsonElement source)
{
    string json = File.ReadAllText(source.GetProperty("fileName").GetString());

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        return doc.RootElement.Clone();
    }
}
```

<span data-ttu-id="420a8-503">前面的代码需要包含 `fileName` 属性的 `JsonElement`。</span><span class="sxs-lookup"><span data-stu-id="420a8-503">The preceding code expects a `JsonElement` that contains a `fileName` property.</span></span> <span data-ttu-id="420a8-504">它会打开 JSON 文件并创建一个 `JsonDocument`。</span><span class="sxs-lookup"><span data-stu-id="420a8-504">It opens the JSON file and creates a `JsonDocument`.</span></span> <span data-ttu-id="420a8-505">该方法假设调用方要处理整个文档，因此会返回 `RootElement` 的 `Clone`。</span><span class="sxs-lookup"><span data-stu-id="420a8-505">The method assumes that the caller wants to work with the entire document, so it returns the `Clone` of the `RootElement`.</span></span>

<span data-ttu-id="420a8-506">如果收到 `JsonElement` 并要返回子元素，则无需返回子元素的 `Clone`。</span><span class="sxs-lookup"><span data-stu-id="420a8-506">If you receive a `JsonElement` and are returning a sub-element, it's not necessary to return a `Clone` of the sub-element.</span></span> <span data-ttu-id="420a8-507">调用方负责使传入的 `JsonElement` 所属的 `JsonDocument` 保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="420a8-507">The caller is responsible for keeping alive the `JsonDocument` that the passed-in `JsonElement` belongs to.</span></span> <span data-ttu-id="420a8-508">例如：</span><span class="sxs-lookup"><span data-stu-id="420a8-508">For example:</span></span>

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a><span data-ttu-id="420a8-509">JsonDocument 为只读</span><span class="sxs-lookup"><span data-stu-id="420a8-509">JsonDocument is read-only</span></span>

<span data-ttu-id="420a8-510"><xref:System.Text.Json> DOM 无法添加、删除或修改 JSON 元素。</span><span class="sxs-lookup"><span data-stu-id="420a8-510">The <xref:System.Text.Json> DOM can't add, remove, or modify JSON elements.</span></span> <span data-ttu-id="420a8-511">它这样设计是为了实现性能，并减少用于分析常见 JSON 有效负载大小（即 < 1 MB）的分配。</span><span class="sxs-lookup"><span data-stu-id="420a8-511">It's designed this way for performance and to reduce allocations for parsing common JSON payload sizes (that is, < 1 MB).</span></span> <span data-ttu-id="420a8-512">如果你的方案当前使用可修改的 DOM，则以下解决方法之一可能是可行的：</span><span class="sxs-lookup"><span data-stu-id="420a8-512">If your scenario currently uses a modifiable DOM, one of the following workarounds might be feasible:</span></span>

* <span data-ttu-id="420a8-513">若要从头开始生成 `JsonDocument`（即，不将现有 JSON 有效负载传入到 `Parse` 方法），请使用 `Utf8JsonWriter` 编写 JSON 文本，并分析这样做的输出以创建新 `JsonDocument`。</span><span class="sxs-lookup"><span data-stu-id="420a8-513">To build a `JsonDocument` from scratch (that is, without passing in an existing JSON payload to the `Parse` method), write the JSON text by using the `Utf8JsonWriter` and parse the output from that to make a new `JsonDocument`.</span></span>
* <span data-ttu-id="420a8-514">若要修改现有 `JsonDocument`，请使用它编写 JSON 文本（在编写时进行更改），并分析这样做的输出以创建新 `JsonDocument`。</span><span class="sxs-lookup"><span data-stu-id="420a8-514">To modify an existing `JsonDocument`, use it to write JSON text, making changes while you write, and parse the output from that to make a new `JsonDocument`.</span></span>
* <span data-ttu-id="420a8-515">若要合并现有 JSON 文档（与 `Newtonsoft.Json` 中的 `JObject.Merge` 或 `JContainer.Merge` API 等效），请参阅[此 GitHub 问题](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853)。</span><span class="sxs-lookup"><span data-stu-id="420a8-515">To merge existing JSON documents, equivalent to the `JObject.Merge` or `JContainer.Merge` APIs from `Newtonsoft.Json`, see [this GitHub issue](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).</span></span>

### <a name="jsonelement-is-a-union-struct"></a><span data-ttu-id="420a8-516">JsonElement 是联合结构</span><span class="sxs-lookup"><span data-stu-id="420a8-516">JsonElement is a union struct</span></span>

<span data-ttu-id="420a8-517">`JsonDocument` 将 `RootElement` 公开为类型 <xref:System.Text.Json.JsonElement> 的属性，该类型是包含任何 JSON 元素的联合结构类型。</span><span class="sxs-lookup"><span data-stu-id="420a8-517">`JsonDocument` exposes the `RootElement` as a property of type <xref:System.Text.Json.JsonElement>, which is a union, struct type that encompasses any JSON element.</span></span> <span data-ttu-id="420a8-518">`Newtonsoft.Json` 使用专用分层类型，如 `JObject`、`JArray`、`JToken` 等。</span><span class="sxs-lookup"><span data-stu-id="420a8-518">`Newtonsoft.Json` uses dedicated hierarchical types like `JObject`,`JArray`, `JToken`, and so forth.</span></span> <span data-ttu-id="420a8-519">`JsonElement` 是可以搜索和枚举的内容，你可以使用 `JsonElement` 将 JSON 元素具体化为 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="420a8-519">`JsonElement` is what you can search and enumerate over, and you can use `JsonElement` to materialize JSON elements into .NET types.</span></span>

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a><span data-ttu-id="420a8-520">如何搜索子元素的 JsonDocument 和 JsonElement</span><span class="sxs-lookup"><span data-stu-id="420a8-520">How to search a JsonDocument and JsonElement for sub-elements</span></span>

<span data-ttu-id="420a8-521">使用 `Newtonsoft.Json` 中的 `JObject` 或 `JArray` 搜索 JSON 令牌的速度往往相对较快，因为它们是在某个字典中查找。</span><span class="sxs-lookup"><span data-stu-id="420a8-521">Searches for JSON tokens using `JObject` or `JArray` from `Newtonsoft.Json` tend to be relatively fast because they're lookups in some dictionary.</span></span> <span data-ttu-id="420a8-522">相比之下，对 `JsonElement` 进行搜索需要对属性进行线性搜索，因此速度相对较慢（例如在使用 `TryGetProperty` 时）。</span><span class="sxs-lookup"><span data-stu-id="420a8-522">By comparison, searches on `JsonElement` require a sequential search of the properties and hence is relatively slow (for example when using `TryGetProperty`).</span></span> <span data-ttu-id="420a8-523"><xref:System.Text.Json> 旨在最大程度减少初始分析时间，而不是查找时间。</span><span class="sxs-lookup"><span data-stu-id="420a8-523"><xref:System.Text.Json> is designed to minimize initial parse time rather than lookup time.</span></span> <span data-ttu-id="420a8-524">因此，在通过 `JsonDocument` 对象搜索时，请使用以下方法优化性能：</span><span class="sxs-lookup"><span data-stu-id="420a8-524">Therefore, use the following approaches to optimize performance when searching through a `JsonDocument` object:</span></span>

* <span data-ttu-id="420a8-525">使用内置枚举器（<xref:System.Text.Json.JsonElement.EnumerateArray%2A> 和 <xref:System.Text.Json.JsonElement.EnumerateObject%2A>），而不是执行自己的索引或循环。</span><span class="sxs-lookup"><span data-stu-id="420a8-525">Use the built-in enumerators (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> and <xref:System.Text.Json.JsonElement.EnumerateObject%2A>) rather than doing your own indexing or loops.</span></span>
* <span data-ttu-id="420a8-526">不要使用 `RootElement` 通过每个属性对整个 `JsonDocument` 执行线性搜索。</span><span class="sxs-lookup"><span data-stu-id="420a8-526">Don't do a sequential search on the whole `JsonDocument` through every property by using `RootElement`.</span></span> <span data-ttu-id="420a8-527">而是基于 JSON 数据的已知结构对嵌套 JSON 对象进行搜索。</span><span class="sxs-lookup"><span data-stu-id="420a8-527">Instead, search on nested JSON objects based on the known structure of the JSON data.</span></span> <span data-ttu-id="420a8-528">例如，如果要在 `Student` 对象中查找 `Grade` 属性，请循环访问 `Student` 对象，并获取每个对象的 `Grade` 值，而不是搜索所有 `Grade` 对象来查找 `JsonElement` 属性。</span><span class="sxs-lookup"><span data-stu-id="420a8-528">For example, if you're looking for a `Grade` property in `Student` objects, loop through the `Student` objects and get the value of `Grade` for each, rather than searching through all `JsonElement` objects looking for `Grade` properties.</span></span> <span data-ttu-id="420a8-529">执行后者将导致不必要浏览相同数据。</span><span class="sxs-lookup"><span data-stu-id="420a8-529">Doing the latter will result in unnecessary passes over the same data.</span></span>

<span data-ttu-id="420a8-530">有关代码示例，请参阅[使用 JsonDocument 访问数据](system-text-json-how-to.md#use-jsondocument-for-access-to-data)。</span><span class="sxs-lookup"><span data-stu-id="420a8-530">For a code example, see [Use JsonDocument for access to data](system-text-json-how-to.md#use-jsondocument-for-access-to-data).</span></span>

## <a name="utf8jsonreader-compared-to-jsontextreader"></a><span data-ttu-id="420a8-531">Utf8JsonReader 与 JsonTextReader 的比较</span><span class="sxs-lookup"><span data-stu-id="420a8-531">Utf8JsonReader compared to JsonTextReader</span></span>

<span data-ttu-id="420a8-532"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> 是面向 UTF-8 编码 JSON 文本的一个高性能、低分配的只进读取器，从 [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) 或 [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) 读取信息。</span><span class="sxs-lookup"><span data-stu-id="420a8-532"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) or [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601).</span></span> <span data-ttu-id="420a8-533">`Utf8JsonReader` 是一种低级类型，可用于生成自定义分析器和反序列化程序。</span><span class="sxs-lookup"><span data-stu-id="420a8-533">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span>

<span data-ttu-id="420a8-534">以下各节说明使用 `Utf8JsonReader` 的推荐编程模式。</span><span class="sxs-lookup"><span data-stu-id="420a8-534">The following sections explain recommended programming patterns for using `Utf8JsonReader`.</span></span>

### <a name="utf8jsonreader-is-a-ref-struct"></a><span data-ttu-id="420a8-535">Utf8JsonReader 是 ref struct</span><span class="sxs-lookup"><span data-stu-id="420a8-535">Utf8JsonReader is a ref struct</span></span>

<span data-ttu-id="420a8-536">由于 `Utf8JsonReader` 类型是 ref struct，因此它具有[某些限制](../../csharp/language-reference/builtin-types/struct.md#ref-struct)。</span><span class="sxs-lookup"><span data-stu-id="420a8-536">Because the `Utf8JsonReader` type is a *ref struct*, it has [certain limitations](../../csharp/language-reference/builtin-types/struct.md#ref-struct).</span></span> <span data-ttu-id="420a8-537">例如，它无法作为字段存储在 ref struct 之外的类或结构中。</span><span class="sxs-lookup"><span data-stu-id="420a8-537">For example, it can't be stored as a field on a class or struct other than a ref struct.</span></span> <span data-ttu-id="420a8-538">若要实现高性能，此类型必须为 `ref struct`，因为它需要缓存输入 [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601)（这本身便是 ref struct）。</span><span class="sxs-lookup"><span data-stu-id="420a8-538">To achieve high performance, this type must be a `ref struct` since it needs to cache the input [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), which itself is a ref struct.</span></span> <span data-ttu-id="420a8-539">此外，此类型是可变的，因为它包含状态。</span><span class="sxs-lookup"><span data-stu-id="420a8-539">In addition, this type is mutable since it holds state.</span></span> <span data-ttu-id="420a8-540">因此，它按引用传递而不是按值传递。</span><span class="sxs-lookup"><span data-stu-id="420a8-540">Therefore, **pass it by ref** rather than by value.</span></span> <span data-ttu-id="420a8-541">按值传递会产生结构副本，状态更改会对调用方不可见。</span><span class="sxs-lookup"><span data-stu-id="420a8-541">Passing it by value would result in a struct copy and the state changes would not be visible to the caller.</span></span> <span data-ttu-id="420a8-542">这与 `Newtonsoft.Json` 不同，因为 `Newtonsoft.Json` `JsonTextReader` 是一个类。</span><span class="sxs-lookup"><span data-stu-id="420a8-542">This differs from `Newtonsoft.Json` since the `Newtonsoft.Json` `JsonTextReader` is a class.</span></span> <span data-ttu-id="420a8-543">有关如何使用 ref struct 的详细信息，请参阅[编写安全有效的 C# 代码](../../csharp/write-safe-efficient-code.md)。</span><span class="sxs-lookup"><span data-stu-id="420a8-543">For more information about how to use ref structs, see [Write safe and efficient C# code](../../csharp/write-safe-efficient-code.md).</span></span>

### <a name="read-utf-8-text"></a><span data-ttu-id="420a8-544">读取 UTF-8 文本</span><span class="sxs-lookup"><span data-stu-id="420a8-544">Read UTF-8 text</span></span>

<span data-ttu-id="420a8-545">若要在使用 `Utf8JsonReader` 时实现可能的最佳性能，请读取已编码为 UTF-8 文本（而不是 UTF-16 字符串）的 JSON 有效负载。</span><span class="sxs-lookup"><span data-stu-id="420a8-545">To achieve the best possible performance while using the `Utf8JsonReader`, read JSON payloads already encoded as UTF-8 text rather than as UTF-16 strings.</span></span> <span data-ttu-id="420a8-546">有关代码示例，请参阅[使用 Utf8JsonReader 筛选数据](system-text-json-how-to.md#filter-data-using-utf8jsonreader)。</span><span class="sxs-lookup"><span data-stu-id="420a8-546">For a code example, see [Filter data using Utf8JsonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader).</span></span>

### <a name="read-with-a-stream-or-pipereader"></a><span data-ttu-id="420a8-547">使用流或 PipeReader 进行读取</span><span class="sxs-lookup"><span data-stu-id="420a8-547">Read with a Stream or PipeReader</span></span>

<span data-ttu-id="420a8-548">`Utf8JsonReader` 支持从 UTF-8 编码的 [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) 或 [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601)（这是从 <xref:System.IO.Pipelines.PipeReader> 读取的结果）进行读取。</span><span class="sxs-lookup"><span data-stu-id="420a8-548">The `Utf8JsonReader` supports reading from a UTF-8 encoded [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) or [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) (which is the result of reading from a <xref:System.IO.Pipelines.PipeReader>).</span></span>

<span data-ttu-id="420a8-549">对于同步读取，可以读取 JSON 有效负载，直到流的末尾进入字节数组中，并将该数组传递给读取器。</span><span class="sxs-lookup"><span data-stu-id="420a8-549">For synchronous reading, you could read the JSON payload until the end of the stream into a byte array and pass that into the reader.</span></span> <span data-ttu-id="420a8-550">若要从字符串（编码为 UTF-16）进行读取，请调用 <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A></span><span class="sxs-lookup"><span data-stu-id="420a8-550">For reading from a string (which is encoded as UTF-16), call <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A></span></span> <span data-ttu-id="420a8-551">以首先将字符串转码为 UTF-8 编码的字节数组。</span><span class="sxs-lookup"><span data-stu-id="420a8-551">to first transcode the string to a UTF-8 encoded byte array.</span></span> <span data-ttu-id="420a8-552">然后将该数组传递给 `Utf8JsonReader`。</span><span class="sxs-lookup"><span data-stu-id="420a8-552">Then pass that to the `Utf8JsonReader`.</span></span>

<span data-ttu-id="420a8-553">由于 `Utf8JsonReader` 将输入视为 JSON 文本，因此 UTF-8 字节顺序标记 (BOM) 被视为无效 JSON。</span><span class="sxs-lookup"><span data-stu-id="420a8-553">Since the `Utf8JsonReader` considers the input to be JSON text, a UTF-8 byte order mark (BOM) is considered invalid JSON.</span></span> <span data-ttu-id="420a8-554">调用方需要在将数据传递给读取器之前将该标记筛选出来。</span><span class="sxs-lookup"><span data-stu-id="420a8-554">The caller needs to filter that out before passing the data to the reader.</span></span>

<span data-ttu-id="420a8-555">有关代码示例，请参阅[使用 Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader)。</span><span class="sxs-lookup"><span data-stu-id="420a8-555">For code examples, see [Use Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader).</span></span>

### <a name="read-with-multi-segment-readonlysequence"></a><span data-ttu-id="420a8-556">使用多段 ReadOnlySequence 进行读取</span><span class="sxs-lookup"><span data-stu-id="420a8-556">Read with multi-segment ReadOnlySequence</span></span>

<span data-ttu-id="420a8-557">如果 JSON 输入是 [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601)，则在运行读取循环时，可以从读取器上的 `ValueSpan` 属性访问每个 JSON 元素。</span><span class="sxs-lookup"><span data-stu-id="420a8-557">If your JSON input is a [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), each JSON element can be accessed from the `ValueSpan` property on the reader as you go through the read loop.</span></span> <span data-ttu-id="420a8-558">但是，如果输入是 [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601)（这是从 <xref:System.IO.Pipelines.PipeReader> 读取的结果），则某些 JSON 元素可能会跨 `ReadOnlySequence<byte>` 对象的多个段。</span><span class="sxs-lookup"><span data-stu-id="420a8-558">However, if your input is a [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) (which is the result of reading from a <xref:System.IO.Pipelines.PipeReader>), some JSON elements might straddle multiple segments of the `ReadOnlySequence<byte>` object.</span></span> <span data-ttu-id="420a8-559">无法在连续内存块中从 <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> 访问这些元素。</span><span class="sxs-lookup"><span data-stu-id="420a8-559">These elements would not be accessible from <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> in a contiguous memory block.</span></span> <span data-ttu-id="420a8-560">而是在每次将多段 `ReadOnlySequence<byte>` 作为输入时，轮询读取器上的 <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> 属性，以确定如何访问当前 JSON 元素。</span><span class="sxs-lookup"><span data-stu-id="420a8-560">Instead, whenever you have a multi-segment `ReadOnlySequence<byte>` as input, poll the <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> property on the reader to figure out how to access the current JSON element.</span></span> <span data-ttu-id="420a8-561">下面是推荐模式：</span><span class="sxs-lookup"><span data-stu-id="420a8-561">Here's a recommended pattern:</span></span>

```csharp
while (reader.Read())
{
    switch (reader.TokenType)
    {
        // ...
        ReadOnlySpan<byte> jsonElement = reader.HasValueSequence ?
            reader.ValueSequence.ToArray() :
            reader.ValueSpan;
        // ...
    }
}
```

### <a name="use-valuetextequals-for-property-name-lookups"></a><span data-ttu-id="420a8-562">使用 ValueTextEquals 进行属性名称查找</span><span class="sxs-lookup"><span data-stu-id="420a8-562">Use ValueTextEquals for property name lookups</span></span>

<span data-ttu-id="420a8-563">不要使用 <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> 通过对属性名称查找调用 <xref:System.MemoryExtensions.SequenceEqual%2A> 来执行逐字节比较。</span><span class="sxs-lookup"><span data-stu-id="420a8-563">Don't use <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> to do byte-by-byte comparisons by calling <xref:System.MemoryExtensions.SequenceEqual%2A> for property name lookups.</span></span> <span data-ttu-id="420a8-564">改为调用 <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A>，因为该方法会对在 JSON 中转义的任何字符取消转义。</span><span class="sxs-lookup"><span data-stu-id="420a8-564">Call <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A> instead, because that method unescapes any characters that are escaped in the JSON.</span></span> <span data-ttu-id="420a8-565">下面的示例演示如何搜索名为“name”的属性：</span><span class="sxs-lookup"><span data-stu-id="420a8-565">Here's an example that shows how to search for a property that is named "name":</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a><span data-ttu-id="420a8-566">将 null 值读取到可为 null 的值类型中</span><span class="sxs-lookup"><span data-stu-id="420a8-566">Read null values into nullable value types</span></span>

<span data-ttu-id="420a8-567">`Newtonsoft.Json` 提供返回 <xref:System.Nullable%601> 的 API，如 `ReadAsBoolean`（它通过返回 `bool?` 来处理 `Null` `TokenType`）。</span><span class="sxs-lookup"><span data-stu-id="420a8-567">`Newtonsoft.Json` provides APIs that return <xref:System.Nullable%601>, such as `ReadAsBoolean`, which handles a `Null` `TokenType` for you by returning a `bool?`.</span></span> <span data-ttu-id="420a8-568">内置 `System.Text.Json` API 仅返回不可为 null 的值类型。</span><span class="sxs-lookup"><span data-stu-id="420a8-568">The built-in `System.Text.Json` APIs return only non-nullable value types.</span></span> <span data-ttu-id="420a8-569">例如，<xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> 返回 `bool`。</span><span class="sxs-lookup"><span data-stu-id="420a8-569">For example, <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> returns a `bool`.</span></span> <span data-ttu-id="420a8-570">如果它在 JSON 中发现 `Null`，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="420a8-570">It throws an exception if it finds `Null` in the JSON.</span></span> <span data-ttu-id="420a8-571">下面的示例演示两种用于处理 null 的方法，一种方法是返回可为 null 的值类型，另一种方法是返回默认值：</span><span class="sxs-lookup"><span data-stu-id="420a8-571">The following examples show two ways to handle nulls, one by returning a nullable value type and one by returning the default value:</span></span>

```csharp
public bool? ReadAsNullableBoolean()
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return null;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

```csharp
public bool ReadAsBoolean(bool defaultValue)
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return defaultValue;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

### <a name="multi-targeting"></a><span data-ttu-id="420a8-572">多目标</span><span class="sxs-lookup"><span data-stu-id="420a8-572">Multi-targeting</span></span>

<span data-ttu-id="420a8-573">如果需要继续为某些目标框架使用 `Newtonsoft.Json`，则可以使用多目标，并具有两种实现。</span><span class="sxs-lookup"><span data-stu-id="420a8-573">If you need to continue to use `Newtonsoft.Json` for certain target frameworks, you can multi-target and have two implementations.</span></span> <span data-ttu-id="420a8-574">但是，这并非易事，需要进行一些 `#ifdefs` 和源文件复制。</span><span class="sxs-lookup"><span data-stu-id="420a8-574">However, this is not trivial and would require some `#ifdefs` and source duplication.</span></span> <span data-ttu-id="420a8-575">共享尽可能多代码的一种方法是围绕 `Utf8JsonReader` 和 `Newtonsoft.Json` `JsonTextReader` 创建 `ref struct` 包装器。</span><span class="sxs-lookup"><span data-stu-id="420a8-575">One way to share as much code as possible is to create a `ref struct` wrapper around `Utf8JsonReader` and `Newtonsoft.Json` `JsonTextReader`.</span></span> <span data-ttu-id="420a8-576">此包装器会统一公共外围应用，同时隔离行为差异。</span><span class="sxs-lookup"><span data-stu-id="420a8-576">This wrapper would unify the public surface area while isolating the behavioral differences.</span></span> <span data-ttu-id="420a8-577">这使你可以隔离主要对类型的构造进行的更改，以及按引用传递新类型。</span><span class="sxs-lookup"><span data-stu-id="420a8-577">This lets you isolate the changes mainly to the construction of the type, along with passing the new type around by reference.</span></span> <span data-ttu-id="420a8-578">下面是 [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) 库遵循的模式：</span><span class="sxs-lookup"><span data-stu-id="420a8-578">This is the pattern that the [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) library follows:</span></span>

* [<span data-ttu-id="420a8-579">UnifiedJsonReader.JsonTextReader.cs</span><span class="sxs-lookup"><span data-stu-id="420a8-579">UnifiedJsonReader.JsonTextReader.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [<span data-ttu-id="420a8-580">UnifiedJsonReader.Utf8JsonReader.cs</span><span class="sxs-lookup"><span data-stu-id="420a8-580">UnifiedJsonReader.Utf8JsonReader.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a><span data-ttu-id="420a8-581">Utf8JsonWriter 与 JsonTextWriter 的比较</span><span class="sxs-lookup"><span data-stu-id="420a8-581">Utf8JsonWriter compared to JsonTextWriter</span></span>

<span data-ttu-id="420a8-582"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> 是一种高性能方式，从常见 .NET 类型（例如，`String`、`Int32` 和 `DateTime`）编写 UTF-8 编码的 JSON 文本。</span><span class="sxs-lookup"><span data-stu-id="420a8-582"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="420a8-583">该编写器是一种低级类型，可用于生成自定义序列化程序。</span><span class="sxs-lookup"><span data-stu-id="420a8-583">The writer is a low-level type that can be used to build custom serializers.</span></span>

<span data-ttu-id="420a8-584">以下各节说明使用 `Utf8JsonWriter` 的推荐编程模式。</span><span class="sxs-lookup"><span data-stu-id="420a8-584">The following sections explain recommended programming patterns for using `Utf8JsonWriter`.</span></span>

### <a name="write-with-utf-8-text"></a><span data-ttu-id="420a8-585">使用 UTF-8 文本进行编写</span><span class="sxs-lookup"><span data-stu-id="420a8-585">Write with UTF-8 text</span></span>

<span data-ttu-id="420a8-586">若要在使用 `Utf8JsonWriter` 时实现可能的最佳性能，请编写已编码为 UTF-8 文本（而不是 UTF-16 字符串）的 JSON 有效负载。</span><span class="sxs-lookup"><span data-stu-id="420a8-586">To achieve the best possible performance while using the `Utf8JsonWriter`, write JSON payloads already encoded as UTF-8 text rather than as UTF-16 strings.</span></span> <span data-ttu-id="420a8-587">使用 <xref:System.Text.Json.JsonEncodedText> 可缓存已知字符串属性名称和值并预先编码为静态，并将这些内容传递给编写器，而不是使用 UTF-16 字符串文本。</span><span class="sxs-lookup"><span data-stu-id="420a8-587">Use <xref:System.Text.Json.JsonEncodedText> to cache and pre-encode known string property names and values as statics, and pass those to the writer, rather than using UTF-16 string literals.</span></span> <span data-ttu-id="420a8-588">这比缓存并使用 UTF-8 字节数组更快。</span><span class="sxs-lookup"><span data-stu-id="420a8-588">This is faster than caching and using UTF-8 byte arrays.</span></span>

<span data-ttu-id="420a8-589">如果需要进行自定义转义，此方法也适用。</span><span class="sxs-lookup"><span data-stu-id="420a8-589">This approach also works if you need to do custom escaping.</span></span> <span data-ttu-id="420a8-590">`System.Text.Json` 不允许在编写字符串时禁用转义。</span><span class="sxs-lookup"><span data-stu-id="420a8-590">`System.Text.Json` doesn't let you disable escaping while writing a string.</span></span> <span data-ttu-id="420a8-591">但是，可以将自己的自定义 <xref:System.Text.Encodings.Web.JavaScriptEncoder> 作为一个选项传入编写器，或创建自己的 `JsonEncodedText` 以使用你的 `JavascriptEncoder` 进行转义，然后编写 `JsonEncodedText` 而不是字符串。</span><span class="sxs-lookup"><span data-stu-id="420a8-591">However, you could pass in your own custom <xref:System.Text.Encodings.Web.JavaScriptEncoder> as an option to the writer, or create your own `JsonEncodedText` that uses your `JavascriptEncoder` to do the escaping, and then write the `JsonEncodedText` instead of the string.</span></span> <span data-ttu-id="420a8-592">有关详细信息，请参阅[自定义字符编码](system-text-json-how-to.md#customize-character-encoding)。</span><span class="sxs-lookup"><span data-stu-id="420a8-592">For more information, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="write-raw-values"></a><span data-ttu-id="420a8-593">编写原始值</span><span class="sxs-lookup"><span data-stu-id="420a8-593">Write raw values</span></span>

<span data-ttu-id="420a8-594">`Newtonsoft.Json` `WriteRawValue` 方法可编写原始 JSON（其中需要值）。</span><span class="sxs-lookup"><span data-stu-id="420a8-594">The `Newtonsoft.Json` `WriteRawValue` method writes raw JSON where a value is expected.</span></span> <span data-ttu-id="420a8-595"><xref:System.Text.Json> 没有直接等效项，但下面是确保仅编写有效 JSON 的解决方法：</span><span class="sxs-lookup"><span data-stu-id="420a8-595"><xref:System.Text.Json> has no direct equivalent, but here's a workaround that ensures only valid JSON is written:</span></span>

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a><span data-ttu-id="420a8-596">自定义字符转义</span><span class="sxs-lookup"><span data-stu-id="420a8-596">Customize character escaping</span></span>

<span data-ttu-id="420a8-597">`JsonTextWriter` 的 [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) 设置提供用于转移所有非 ASCII 字符或 HTML 字符的选项。</span><span class="sxs-lookup"><span data-stu-id="420a8-597">The [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) setting of `JsonTextWriter` offers options to escape all non-ASCII characters **or** HTML characters.</span></span> <span data-ttu-id="420a8-598">默认情况下，`Utf8JsonWriter` 会转义所有非 ASCII 和 HTML 字符。</span><span class="sxs-lookup"><span data-stu-id="420a8-598">By default, `Utf8JsonWriter` escapes all non-ASCII **and** HTML characters.</span></span> <span data-ttu-id="420a8-599">进行此转义是出于深度防御安全原因。</span><span class="sxs-lookup"><span data-stu-id="420a8-599">This escaping is done for defense-in-depth security reasons.</span></span> <span data-ttu-id="420a8-600">若要指定不同的转义策略，请创建 <xref:System.Text.Encodings.Web.JavaScriptEncoder> 并设置 <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="420a8-600">To specify a different escaping policy, create a <xref:System.Text.Encodings.Web.JavaScriptEncoder> and set <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>.</span></span> <span data-ttu-id="420a8-601">有关详细信息，请参阅[自定义字符编码](system-text-json-how-to.md#customize-character-encoding)。</span><span class="sxs-lookup"><span data-stu-id="420a8-601">For more information, see [Customize character encoding](system-text-json-how-to.md#customize-character-encoding).</span></span>

### <a name="customize-json-format"></a><span data-ttu-id="420a8-602">自定义 JSON 格式</span><span class="sxs-lookup"><span data-stu-id="420a8-602">Customize JSON format</span></span>

<span data-ttu-id="420a8-603">`JsonTextWriter` 包含以下设置（`Utf8JsonWriter` 对于它们没有等效项）：</span><span class="sxs-lookup"><span data-stu-id="420a8-603">`JsonTextWriter` includes the following settings, for which `Utf8JsonWriter` has no equivalent:</span></span>

* <span data-ttu-id="420a8-604">[缩进](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) - 指定要缩进的字符数。</span><span class="sxs-lookup"><span data-stu-id="420a8-604">[Indentation](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) - Specifies how many characters to indent.</span></span> <span data-ttu-id="420a8-605">`Utf8JsonWriter` 始终执行 2 字符缩进。</span><span class="sxs-lookup"><span data-stu-id="420a8-605">`Utf8JsonWriter` always does 2-character indentation.</span></span>
* <span data-ttu-id="420a8-606">[IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) - 指定要用于缩进的字符。</span><span class="sxs-lookup"><span data-stu-id="420a8-606">[IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) - Specifies the character to use for indentation.</span></span>  <span data-ttu-id="420a8-607">`Utf8JsonWriter` 始终使用空格。</span><span class="sxs-lookup"><span data-stu-id="420a8-607">`Utf8JsonWriter` always uses whitespace.</span></span>
* <span data-ttu-id="420a8-608">[QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) - 指定要用于围绕字符串值的字符。</span><span class="sxs-lookup"><span data-stu-id="420a8-608">[QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) - Specifies the character to use to surround string values.</span></span>  <span data-ttu-id="420a8-609">`Utf8JsonWriter` 始终使用双引号。</span><span class="sxs-lookup"><span data-stu-id="420a8-609">`Utf8JsonWriter` always uses double quotes.</span></span>
* <span data-ttu-id="420a8-610">[QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) - 指定是否要使用引号围绕属性名称。</span><span class="sxs-lookup"><span data-stu-id="420a8-610">[QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) - Specifies whether or not to surround property names with quotes.</span></span>  <span data-ttu-id="420a8-611">`Utf8JsonWriter` 始终使用引号围绕它们。</span><span class="sxs-lookup"><span data-stu-id="420a8-611">`Utf8JsonWriter` always surrounds them with quotes.</span></span>

<span data-ttu-id="420a8-612">没有解决方法可让你自定义 `Utf8JsonWriter` 以这些方式生成的 JSON。</span><span class="sxs-lookup"><span data-stu-id="420a8-612">There are no workarounds that would let you customize the JSON produced by `Utf8JsonWriter` in these ways.</span></span>

### <a name="write-null-values"></a><span data-ttu-id="420a8-613">编写 null 值</span><span class="sxs-lookup"><span data-stu-id="420a8-613">Write null values</span></span>

<span data-ttu-id="420a8-614">若要使用 `Utf8JsonWriter` 编写 null 值，请调用：</span><span class="sxs-lookup"><span data-stu-id="420a8-614">To write null values by using `Utf8JsonWriter`, call:</span></span>

* <span data-ttu-id="420a8-615"><xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A>，用于将具有 null 的键值对编写为值。</span><span class="sxs-lookup"><span data-stu-id="420a8-615"><xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A> to write a key-value pair with null as the value.</span></span>
* <span data-ttu-id="420a8-616"><xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A>用于将 null 编写为 JSON 数组的元素。</span><span class="sxs-lookup"><span data-stu-id="420a8-616"><xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A> to write null as an element of a JSON array.</span></span>

<span data-ttu-id="420a8-617">对于字符串属性，如果字符串为 null，则 <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> 和 <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> 等效于 `WriteNull` 和 `WriteNullValue`。</span><span class="sxs-lookup"><span data-stu-id="420a8-617">For a string property, if the string is null, <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> and <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> are equivalent to `WriteNull` and `WriteNullValue`.</span></span>

### <a name="write-timespan-uri-or-char-values"></a><span data-ttu-id="420a8-618">编写 Timespan、Uri 或 char 值</span><span class="sxs-lookup"><span data-stu-id="420a8-618">Write Timespan, Uri, or char values</span></span>

<span data-ttu-id="420a8-619">`JsonTextWriter` 提供 `WriteValue` 方法以用于 [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm)、[Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm) 和 [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) 值。</span><span class="sxs-lookup"><span data-stu-id="420a8-619">`JsonTextWriter` provides `WriteValue` methods for [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm), and [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) values.</span></span> <span data-ttu-id="420a8-620">`Utf8JsonWriter` 没有等效方法。</span><span class="sxs-lookup"><span data-stu-id="420a8-620">`Utf8JsonWriter` doesn't have equivalent methods.</span></span> <span data-ttu-id="420a8-621">而是将这些值格式化为字符串（例如，通过调用 `ToString()`）并调用 <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>。</span><span class="sxs-lookup"><span data-stu-id="420a8-621">Instead, format these values as strings (by calling `ToString()`, for example) and call <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>.</span></span>

### <a name="multi-targeting"></a><span data-ttu-id="420a8-622">多目标</span><span class="sxs-lookup"><span data-stu-id="420a8-622">Multi-targeting</span></span>

<span data-ttu-id="420a8-623">如果需要继续为某些目标框架使用 `Newtonsoft.Json`，则可以使用多目标，并具有两种实现。</span><span class="sxs-lookup"><span data-stu-id="420a8-623">If you need to continue to use `Newtonsoft.Json` for certain target frameworks, you can multi-target and have two implementations.</span></span> <span data-ttu-id="420a8-624">但是，这并非易事，需要进行一些 `#ifdefs` 和源文件复制。</span><span class="sxs-lookup"><span data-stu-id="420a8-624">However, this is not trivial and would require some `#ifdefs` and source duplication.</span></span> <span data-ttu-id="420a8-625">共享尽可能多代码的一种方法是围绕 `Utf8JsonWriter` 和 `Newtonsoft` `JsonTextWriter` 创建包装器。</span><span class="sxs-lookup"><span data-stu-id="420a8-625">One way to share as much code as possible is to create a wrapper around `Utf8JsonWriter` and `Newtonsoft` `JsonTextWriter`.</span></span> <span data-ttu-id="420a8-626">此包装器会统一公共外围应用，同时隔离行为差异。</span><span class="sxs-lookup"><span data-stu-id="420a8-626">This wrapper would unify the public surface area while isolating the behavioral differences.</span></span> <span data-ttu-id="420a8-627">这使你可以隔离主要对类型的构造进行的更改。</span><span class="sxs-lookup"><span data-stu-id="420a8-627">This lets you isolate the changes mainly to the construction of the type.</span></span> <span data-ttu-id="420a8-628">[Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) 库遵循：</span><span class="sxs-lookup"><span data-stu-id="420a8-628">[Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) library follows:</span></span>

* [<span data-ttu-id="420a8-629">UnifiedJsonWriter.JsonTextWriter.cs</span><span class="sxs-lookup"><span data-stu-id="420a8-629">UnifiedJsonWriter.JsonTextWriter.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [<span data-ttu-id="420a8-630">UnifiedJsonWriter.Utf8JsonWriter.cs</span><span class="sxs-lookup"><span data-stu-id="420a8-630">UnifiedJsonWriter.Utf8JsonWriter.cs</span></span>](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a><span data-ttu-id="420a8-631">其他资源</span><span class="sxs-lookup"><span data-stu-id="420a8-631">Additional resources</span></span>

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* <span data-ttu-id="420a8-632">[System.Text.Json 概述](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="420a8-632">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* <span data-ttu-id="420a8-633">[如何使用 System.Text.Json](system-text-json-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="420a8-633">[How to use System.Text.Json](system-text-json-how-to.md)</span></span>
* [<span data-ttu-id="420a8-634">如何编写自定义转换器</span><span class="sxs-lookup"><span data-stu-id="420a8-634">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="420a8-635">[System.Text.Json 中的 DateTime 和 DateTimeOffset 支持](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="420a8-635">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="420a8-636">[System.Text.Json API 参考](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="420a8-636">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="420a8-637">[System.Text.Json.Serialization API 参考](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="420a8-637">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
