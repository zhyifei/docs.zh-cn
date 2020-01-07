---
title: Xamarin 限制
ms.date: 12/13/2019
description: 介绍使用 Xamarin 时可能会遇到的一些限制。
ms.openlocfilehash: 192f25954726919dc66d706e755e0853404b4d85
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450404"
---
# <a name="xamarin-limitations"></a><span data-ttu-id="09d72-103">Xamarin 限制</span><span class="sxs-lookup"><span data-stu-id="09d72-103">Xamarin limitations</span></span>

<span data-ttu-id="09d72-104">.NET Standard 2.0 的目标，并且在 Xamarin 上受支持。</span><span class="sxs-lookup"><span data-stu-id="09d72-104">Microsoft.Data.Sqlite targets .NET Standard 2.0 and is supported on Xamarin.</span></span> <span data-ttu-id="09d72-105">下表显示默认 SQLitePCLRaw 捆绑为其提供本机 SQLite 二进制文件的平台。</span><span class="sxs-lookup"><span data-stu-id="09d72-105">The following table shows which platforms the default SQLitePCLRaw bundle provides native SQLite binaries for.</span></span> <span data-ttu-id="09d72-106">有关使用不同绑定的详细信息，请参阅[自定义 SQLite 版本](custom-versions.md)，或提供自己的本机 SQLite 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="09d72-106">See [Custom SQLite versions](custom-versions.md) for details on using a different bundle or providing your own native SQLite binaries.</span></span>

| <span data-ttu-id="09d72-107">Platform</span><span class="sxs-lookup"><span data-stu-id="09d72-107">Platform</span></span> | <span data-ttu-id="09d72-108">SQLite 二进制文件</span><span class="sxs-lookup"><span data-stu-id="09d72-108">SQLite binaries</span></span> |
| --- | --- |
| <span data-ttu-id="09d72-109">**Xamarin.Android**</span><span class="sxs-lookup"><span data-stu-id="09d72-109">**Xamarin.Android**</span></span> | <span data-ttu-id="09d72-110">—</span><span class="sxs-lookup"><span data-stu-id="09d72-110">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64-v8a` | <span data-ttu-id="09d72-111">✔</span><span class="sxs-lookup"><span data-stu-id="09d72-111">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`armeabi-v7a` | <span data-ttu-id="09d72-112">✔</span><span class="sxs-lookup"><span data-stu-id="09d72-112">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="09d72-113">✔</span><span class="sxs-lookup"><span data-stu-id="09d72-113">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86_64` | <span data-ttu-id="09d72-114">✔</span><span class="sxs-lookup"><span data-stu-id="09d72-114">✔</span></span> |
| <span data-ttu-id="09d72-115">**Xamarin.iOS**</span><span class="sxs-lookup"><span data-stu-id="09d72-115">**Xamarin.iOS**</span></span> | <span data-ttu-id="09d72-116">✔</span><span class="sxs-lookup"><span data-stu-id="09d72-116">✔</span></span> |
| <span data-ttu-id="09d72-117">**Xamarin.Mac**</span><span class="sxs-lookup"><span data-stu-id="09d72-117">**Xamarin.Mac**</span></span> | <span data-ttu-id="09d72-118">✔</span><span class="sxs-lookup"><span data-stu-id="09d72-118">✔</span></span> |
| <span data-ttu-id="09d72-119">**Xamarin. TVOS**</span><span class="sxs-lookup"><span data-stu-id="09d72-119">**Xamarin.TVOS**</span></span> | <span data-ttu-id="09d72-120">✔</span><span class="sxs-lookup"><span data-stu-id="09d72-120">✔</span></span> |
| <span data-ttu-id="09d72-121">**UWP**</span><span class="sxs-lookup"><span data-stu-id="09d72-121">**UWP**</span></span> | <span data-ttu-id="09d72-122">—</span><span class="sxs-lookup"><span data-stu-id="09d72-122">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm` | <span data-ttu-id="09d72-123">✔</span><span class="sxs-lookup"><span data-stu-id="09d72-123">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64` | <span data-ttu-id="09d72-124">✔</span><span class="sxs-lookup"><span data-stu-id="09d72-124">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x64` | <span data-ttu-id="09d72-125">✔</span><span class="sxs-lookup"><span data-stu-id="09d72-125">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="09d72-126">✔</span><span class="sxs-lookup"><span data-stu-id="09d72-126">✔</span></span> |

## <a name="ios"></a><span data-ttu-id="09d72-127">iOS</span><span class="sxs-lookup"><span data-stu-id="09d72-127">iOS</span></span>

<span data-ttu-id="09d72-128">SQLitePCLRaw 尝试自动初始化捆绑。</span><span class="sxs-lookup"><span data-stu-id="09d72-128">Microsoft.Data.Sqlite tries to automatically initialize SQLitePCLRaw bundles.</span></span> <span data-ttu-id="09d72-129">遗憾的是，由于针对 Xamarin 的预先（AOT）编译存在限制，尝试失败，并出现以下错误。</span><span class="sxs-lookup"><span data-stu-id="09d72-129">Unfortunately, because of limitations in the ahead-of-time (AOT) compilation for Xamarin.iOS, the attempt fails and you get the following error.</span></span>

> <span data-ttu-id="09d72-130">需要调用 `SQLitePCL.raw.SetProvider()`。</span><span class="sxs-lookup"><span data-stu-id="09d72-130">You need to call `SQLitePCL.raw.SetProvider()`.</span></span> <span data-ttu-id="09d72-131">如果使用的是捆绑包，可以通过调用 `SQLitePCL.Batteries.Init()`来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="09d72-131">If you're using a bundle package, this is done by calling `SQLitePCL.Batteries.Init()`.</span></span>

<span data-ttu-id="09d72-132">若要初始化该绑定，请在使用 Microsoft. Sqlite 之前，将以下代码行添加到应用中。</span><span class="sxs-lookup"><span data-stu-id="09d72-132">To initialize the bundle, add the following line of code to your app before using Microsoft.Data.Sqlite.</span></span>

```csharp
SQLitePCL.Batteries_V2.Init();
```

## <a name="see-also"></a><span data-ttu-id="09d72-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09d72-133">See also</span></span>

* [<span data-ttu-id="09d72-134">异步限制</span><span class="sxs-lookup"><span data-stu-id="09d72-134">Async limitations</span></span>](async.md)
* [<span data-ttu-id="09d72-135">自定义 SQLite 版本</span><span class="sxs-lookup"><span data-stu-id="09d72-135">Custom SQLite versions</span></span>](custom-versions.md)
