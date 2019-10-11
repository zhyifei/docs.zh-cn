---
title: 使用C# -.NET 对 JSON 进行序列化和反序列化
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: 5ce98a7908470a402779436db43333d46f5101fc
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180155"
---
# <a name="json-serialization-in-net---overview"></a><span data-ttu-id="85bec-102">.NET 中的 JSON 序列化-概述</span><span class="sxs-lookup"><span data-stu-id="85bec-102">JSON serialization in .NET - overview</span></span>

<span data-ttu-id="85bec-103">@No__t 的命名空间提供了用于序列化和反序列化 JavaScript 对象表示法（JSON）的功能。</span><span class="sxs-lookup"><span data-stu-id="85bec-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="85bec-104">库设计通过广泛的功能集强调高性能和低内存分配。</span><span class="sxs-lookup"><span data-stu-id="85bec-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="85bec-105">内置 UTF-8 支持优化了编码为 UTF-8 的 JSON 文本的处理过程，这是针对 web 上的数据和磁盘上的文件的最流行的编码。</span><span class="sxs-lookup"><span data-stu-id="85bec-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="85bec-106">该库还提供了用于处理内存中文档对象模型（DOM）的类。</span><span class="sxs-lookup"><span data-stu-id="85bec-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="85bec-107">此功能允许对 JSON 文件或字符串中的元素进行随机只读访问。</span><span class="sxs-lookup"><span data-stu-id="85bec-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span> 

## <a name="how-to-get-the-library"></a><span data-ttu-id="85bec-108">如何获取库</span><span class="sxs-lookup"><span data-stu-id="85bec-108">How to get the library</span></span>

* <span data-ttu-id="85bec-109">该库作为[.Net Core 3.0](https://aka.ms/netcore3download)共享框架的一部分内置。</span><span class="sxs-lookup"><span data-stu-id="85bec-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="85bec-110">对于其他目标框架，请安装[System.object](https://www.nuget.org/packages/System.Text.Json) NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="85bec-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="85bec-111">包支持：</span><span class="sxs-lookup"><span data-stu-id="85bec-111">The package supports:</span></span>
  * <span data-ttu-id="85bec-112">.NET Standard 2.0 及更高版本</span><span class="sxs-lookup"><span data-stu-id="85bec-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="85bec-113">.NET Framework 4.6.1 和更高版本</span><span class="sxs-lookup"><span data-stu-id="85bec-113">.NET Framework 4.6.1 and later versions</span></span>
  * <span data-ttu-id="85bec-114">.NET Core 2.0、2.1 和2。2</span><span class="sxs-lookup"><span data-stu-id="85bec-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="85bec-115">其他资源</span><span class="sxs-lookup"><span data-stu-id="85bec-115">Additional resources</span></span>

* [<span data-ttu-id="85bec-116">如何使用库</span><span class="sxs-lookup"><span data-stu-id="85bec-116">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="85bec-117">源代码</span><span class="sxs-lookup"><span data-stu-id="85bec-117">Source code</span></span>](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json)
* [<span data-ttu-id="85bec-118">API 参考</span><span class="sxs-lookup"><span data-stu-id="85bec-118">API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="85bec-119">路线图</span><span class="sxs-lookup"><span data-stu-id="85bec-119">Roadmap</span></span>](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/roadmap/README.md)
* <span data-ttu-id="85bec-120">Dotnet/corefx 存储库中的 GitHub 问题</span><span class="sxs-lookup"><span data-stu-id="85bec-120">GitHub issues in the dotnet/corefx repository</span></span>
  * [<span data-ttu-id="85bec-121">有关系统开发的讨论</span><span class="sxs-lookup"><span data-stu-id="85bec-121">Discussion about the development of System.Text.Json</span></span>](https://github.com/dotnet/corefx/issues/33115)
  * [<span data-ttu-id="85bec-122">所有系统问题</span><span class="sxs-lookup"><span data-stu-id="85bec-122">All System.Text.Json issues</span></span>](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)
  * [<span data-ttu-id="85bec-123">标记为 json 功能的 system.web 问题-doc</span><span class="sxs-lookup"><span data-stu-id="85bec-123">System.Text.Json issues labeled json-functionality-doc</span></span>](https://github.com/dotnet/corefx/labels/json-functionality-doc)
