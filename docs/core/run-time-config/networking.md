---
title: 网络配置设置
description: 了解为 .NET Core 应用配置网络的运行时设置。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 8d02087ad7260cc78c096090bf3b06a716d34678
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989098"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="a42ca-103">用于网络的运行时配置选项</span><span class="sxs-lookup"><span data-stu-id="a42ca-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="a42ca-104">HTTP/2 协议</span><span class="sxs-lookup"><span data-stu-id="a42ca-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="a42ca-105">配置是否启用对 HTTP/2 协议的支持。</span><span class="sxs-lookup"><span data-stu-id="a42ca-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="a42ca-106">默认：禁用 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="a42ca-106">Default: Disabled (`false`).</span></span>

- <span data-ttu-id="a42ca-107">已在 .NET Core 3.0 中引入。</span><span class="sxs-lookup"><span data-stu-id="a42ca-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="a42ca-108">设置名</span><span class="sxs-lookup"><span data-stu-id="a42ca-108">Setting name</span></span> | <span data-ttu-id="a42ca-109">值</span><span class="sxs-lookup"><span data-stu-id="a42ca-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a42ca-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a42ca-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="a42ca-111">`false` - 禁用</span><span class="sxs-lookup"><span data-stu-id="a42ca-111">`false` - disabled</span></span><br/><span data-ttu-id="a42ca-112">`true` - 启用</span><span class="sxs-lookup"><span data-stu-id="a42ca-112">`true` - enabled</span></span> |
| <span data-ttu-id="a42ca-113">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="a42ca-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="a42ca-114">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="a42ca-114">`0` - disabled</span></span><br/><span data-ttu-id="a42ca-115">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="a42ca-115">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="a42ca-116">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="a42ca-116">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="a42ca-117">配置 <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> 是使用 <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> 还是使用旧的 HTTP 协议堆栈（在 Windows 上为 <xref:System.Net.Http.WinHttpHandler>，在 Linux 上为基于 [libcurl](https://curl.haxx.se/libcurl/) 实现的内部类 `CurlHandler`。）</span><span class="sxs-lookup"><span data-stu-id="a42ca-117">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a42ca-118">可使用高级别网络 API，而不是直接实例化 <xref:System.Net.Http.HttpClientHandler> 类。</span><span class="sxs-lookup"><span data-stu-id="a42ca-118">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="a42ca-119">此设置还会影响高级别网络 API 使用的 HTTP 协议堆栈类型，包括 <xref:System.Net.Http.HttpClient> 和 [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118))。</span><span class="sxs-lookup"><span data-stu-id="a42ca-119">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span></span>

- <span data-ttu-id="a42ca-120">默认：使用 <xref:System.Net.Http.SocketsHttpHandler> (`true`)。</span><span class="sxs-lookup"><span data-stu-id="a42ca-120">Default: Use <xref:System.Net.Http.SocketsHttpHandler> (`true`).</span></span>

- <span data-ttu-id="a42ca-121">可通过调用 <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 方法，以编程方式配置此设置。</span><span class="sxs-lookup"><span data-stu-id="a42ca-121">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="a42ca-122">设置名</span><span class="sxs-lookup"><span data-stu-id="a42ca-122">Setting name</span></span> | <span data-ttu-id="a42ca-123">值</span><span class="sxs-lookup"><span data-stu-id="a42ca-123">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a42ca-124">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a42ca-124">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="a42ca-125">`true` - 允许使用 <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="a42ca-125">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="a42ca-126">`false` - 允许使用 Windows 上的 <xref:System.Net.Http.WinHttpHandler> 或 Linux 上的 [libcurl](https://curl.haxx.se/libcurl/)</span><span class="sxs-lookup"><span data-stu-id="a42ca-126">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="a42ca-127">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="a42ca-127">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="a42ca-128">`1` - 允许使用 <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="a42ca-128">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="a42ca-129">`0` - 允许使用 Windows 上的 <xref:System.Net.Http.WinHttpHandler> 或 Linux 上的 [libcurl](https://curl.haxx.se/libcurl/)</span><span class="sxs-lookup"><span data-stu-id="a42ca-129">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="a42ca-130">从 .NET 5 开始，`System.Net.Http.UseSocketsHttpHandler` 设置不再可用。</span><span class="sxs-lookup"><span data-stu-id="a42ca-130">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
