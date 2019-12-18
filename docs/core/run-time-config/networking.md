---
title: 网络配置设置
description: 了解为 .NET Core 应用配置网络的运行时设置。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 622c4afbd36d3d9004edbd9219145fa9e5d326ae
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998833"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="852f7-103">用于网络的运行时配置选项</span><span class="sxs-lookup"><span data-stu-id="852f7-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="852f7-104">HTTP/2 协议</span><span class="sxs-lookup"><span data-stu-id="852f7-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="852f7-105">配置是否启用对 HTTP/2 协议的支持。</span><span class="sxs-lookup"><span data-stu-id="852f7-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>
- <span data-ttu-id="852f7-106">默认：禁用 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="852f7-106">Default: Disabled (`false`).</span></span>
- <span data-ttu-id="852f7-107">已在 .NET Core 3.0 中引入。</span><span class="sxs-lookup"><span data-stu-id="852f7-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="852f7-108">设置名</span><span class="sxs-lookup"><span data-stu-id="852f7-108">Setting name</span></span> | <span data-ttu-id="852f7-109">值</span><span class="sxs-lookup"><span data-stu-id="852f7-109">Values</span></span> |
| - | - |
| <span data-ttu-id="852f7-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="852f7-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="852f7-111">`false` - 禁用</span><span class="sxs-lookup"><span data-stu-id="852f7-111">`false` - disabled</span></span><br/><span data-ttu-id="852f7-112">`true` - 启用</span><span class="sxs-lookup"><span data-stu-id="852f7-112">`true` - enabled</span></span> |
| <span data-ttu-id="852f7-113">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="852f7-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="852f7-114">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="852f7-114">`0` - disabled</span></span><br/><span data-ttu-id="852f7-115">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="852f7-115">`1` - enabled</span></span> |

## <a name="sockets-http-handler"></a><span data-ttu-id="852f7-116">套接字 HTTP 处理程序</span><span class="sxs-lookup"><span data-stu-id="852f7-116">Sockets HTTP handler</span></span>

- <span data-ttu-id="852f7-117">配置高级网络 API（如 <xref:System.Net.Http.HttpClient>）是使用 <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>，还是使用基于 [libcurl](https://curl.haxx.se/libcurl/) 的 <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> 实现。</span><span class="sxs-lookup"><span data-stu-id="852f7-117">Configures whether high-level networking APIs, such as <xref:System.Net.Http.HttpClient>, use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or the implementation of <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> that's based on [libcurl](https://curl.haxx.se/libcurl/).</span></span>
- <span data-ttu-id="852f7-118">默认：使用 <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`)。</span><span class="sxs-lookup"><span data-stu-id="852f7-118">Default: Use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).</span></span>
- <span data-ttu-id="852f7-119">可通过调用 <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 方法，以编程方式配置此设置。</span><span class="sxs-lookup"><span data-stu-id="852f7-119">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="852f7-120">设置名</span><span class="sxs-lookup"><span data-stu-id="852f7-120">Setting name</span></span> | <span data-ttu-id="852f7-121">值</span><span class="sxs-lookup"><span data-stu-id="852f7-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="852f7-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="852f7-122">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="852f7-123">`true` - 允许使用 <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="852f7-123">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="852f7-124">`false` - 允许使用 <xref:System.Net.Http.HttpClientHandler></span><span class="sxs-lookup"><span data-stu-id="852f7-124">`false` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
| <span data-ttu-id="852f7-125">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="852f7-125">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="852f7-126">`1` - 允许使用 <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="852f7-126">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="852f7-127">`0` - 允许使用 <xref:System.Net.Http.HttpClientHandler></span><span class="sxs-lookup"><span data-stu-id="852f7-127">`0` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
