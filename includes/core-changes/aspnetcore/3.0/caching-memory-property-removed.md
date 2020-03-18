---
ms.openlocfilehash: 2c1362d6982206b14475f77700add0bae61da173
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901755"
---
### <a name="caching-compactonmemorypressure-property-removed"></a><span data-ttu-id="1bc60-101">缓存：已删除 CompactOnMemoryPressure 属性</span><span class="sxs-lookup"><span data-stu-id="1bc60-101">Caching: CompactOnMemoryPressure property removed</span></span>

<span data-ttu-id="1bc60-102">ASP.NET Core 3.0 版本已删除[过时的 MemoryCacheOptions API](https://github.com/dotnet/extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18)。</span><span class="sxs-lookup"><span data-stu-id="1bc60-102">The ASP.NET Core 3.0 release removed the [obsolete MemoryCacheOptions APIs](https://github.com/dotnet/extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18).</span></span>

#### <a name="change-description"></a><span data-ttu-id="1bc60-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="1bc60-103">Change description</span></span>

<span data-ttu-id="1bc60-104">此更改是对 [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221) 的后续补充。</span><span class="sxs-lookup"><span data-stu-id="1bc60-104">This change is a follow-up to [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221).</span></span> <span data-ttu-id="1bc60-105">有关讨论，请参阅 [dotnet/extensions#1062](https://github.com/dotnet/extensions/issues/1062)。</span><span class="sxs-lookup"><span data-stu-id="1bc60-105">For discussion, see [dotnet/extensions#1062](https://github.com/dotnet/extensions/issues/1062).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1bc60-106">引入的版本</span><span class="sxs-lookup"><span data-stu-id="1bc60-106">Version introduced</span></span>

<span data-ttu-id="1bc60-107">3.0</span><span class="sxs-lookup"><span data-stu-id="1bc60-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="1bc60-108">旧行为</span><span class="sxs-lookup"><span data-stu-id="1bc60-108">Old behavior</span></span>

<span data-ttu-id="1bc60-109">`MemoryCacheOptions.CompactOnMemoryPressure` 属性可用。</span><span class="sxs-lookup"><span data-stu-id="1bc60-109">`MemoryCacheOptions.CompactOnMemoryPressure` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="1bc60-110">新行为</span><span class="sxs-lookup"><span data-stu-id="1bc60-110">New behavior</span></span>

<span data-ttu-id="1bc60-111">`MemoryCacheOptions.CompactOnMemoryPressure` 属性已被删除。</span><span class="sxs-lookup"><span data-stu-id="1bc60-111">The `MemoryCacheOptions.CompactOnMemoryPressure` property has been removed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1bc60-112">更改原因</span><span class="sxs-lookup"><span data-stu-id="1bc60-112">Reason for change</span></span>

<span data-ttu-id="1bc60-113">自动压缩缓存会引起问题。</span><span class="sxs-lookup"><span data-stu-id="1bc60-113">Automatically compacting the cache caused problems.</span></span> <span data-ttu-id="1bc60-114">若要避免意外行为，只应在需要时压缩缓存。</span><span class="sxs-lookup"><span data-stu-id="1bc60-114">To avoid unexpected behavior, the cache should only be compacted when needed.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1bc60-115">建议操作</span><span class="sxs-lookup"><span data-stu-id="1bc60-115">Recommended action</span></span>

<span data-ttu-id="1bc60-116">若要压缩缓存，请向下转换到 `MemoryCache` 并在需要时调用 `Compact`。</span><span class="sxs-lookup"><span data-stu-id="1bc60-116">To compact the cache, downcast to `MemoryCache` and call `Compact` when needed.</span></span>

#### <a name="category"></a><span data-ttu-id="1bc60-117">类别</span><span class="sxs-lookup"><span data-stu-id="1bc60-117">Category</span></span>

<span data-ttu-id="1bc60-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1bc60-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1bc60-119">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="1bc60-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->
