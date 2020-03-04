---
title: 使用C# -.NET 对 JSON 进行序列化和反序列化
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 660a2831aa6a807486fc47eae880bcd11347c547
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159541"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="e84de-102">.NET 中的 JSON 序列化和反序列化（封送和 unmarshalling）-概述</span><span class="sxs-lookup"><span data-stu-id="e84de-102">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="e84de-103">`System.Text.Json` 命名空间提供用于序列化和反序列化 JavaScript 对象表示法（JSON）的功能。</span><span class="sxs-lookup"><span data-stu-id="e84de-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="e84de-104">库设计通过广泛的功能集强调高性能和低内存分配。</span><span class="sxs-lookup"><span data-stu-id="e84de-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="e84de-105">内置 UTF-8 支持优化了编码为 UTF-8 的 JSON 文本的处理过程，这是针对 web 上的数据和磁盘上的文件的最流行的编码。</span><span class="sxs-lookup"><span data-stu-id="e84de-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="e84de-106">该库还提供了用于处理内存中文档对象模型（DOM）的类。</span><span class="sxs-lookup"><span data-stu-id="e84de-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="e84de-107">此功能允许对 JSON 文件或字符串中的元素进行随机只读访问。</span><span class="sxs-lookup"><span data-stu-id="e84de-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span>

## <a name="how-to-get-the-library"></a><span data-ttu-id="e84de-108">如何获取库</span><span class="sxs-lookup"><span data-stu-id="e84de-108">How to get the library</span></span>

* <span data-ttu-id="e84de-109">该库作为[.Net Core 3.0](https://aka.ms/netcore3download)共享框架的一部分内置。</span><span class="sxs-lookup"><span data-stu-id="e84de-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="e84de-110">对于其他目标框架，请安装[System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="e84de-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="e84de-111">包支持：</span><span class="sxs-lookup"><span data-stu-id="e84de-111">The package supports:</span></span>
  * <span data-ttu-id="e84de-112">.NET Standard 2.0 及更高版本</span><span class="sxs-lookup"><span data-stu-id="e84de-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="e84de-113">.NET Framework 4.7.2 和更高版本</span><span class="sxs-lookup"><span data-stu-id="e84de-113">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="e84de-114">.NET Core 2.0、2.1 和2.2</span><span class="sxs-lookup"><span data-stu-id="e84de-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e84de-115">其他资源</span><span class="sxs-lookup"><span data-stu-id="e84de-115">Additional resources</span></span>

* [<span data-ttu-id="e84de-116">如何使用库</span><span class="sxs-lookup"><span data-stu-id="e84de-116">How to use the library</span></span>](system-text-json-how-to.md)
* <span data-ttu-id="e84de-117">[如何从 Newtonsoft.Json 迁移](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="e84de-117">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* [<span data-ttu-id="e84de-118">如何编写转换器</span><span class="sxs-lookup"><span data-stu-id="e84de-118">How to write converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="e84de-119">[System.Text.Json 源代码](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="e84de-119">[System.Text.Json source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span></span>
* <span data-ttu-id="e84de-120">[System.Text.Json API 参考](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="e84de-120">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="e84de-121">[System.Text.Json。序列化 API 参考](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="e84de-121">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
