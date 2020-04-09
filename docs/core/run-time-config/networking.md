---
title: 网络配置设置
description: 了解为 .NET Core 应用配置网络的运行时设置。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: f5ea47f0444a911dc2347a66817cabf585fd8e70
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635427"
---
# <a name="run-time-configuration-options-for-networking"></a>用于网络的运行时配置选项

## <a name="http2-protocol"></a>HTTP/2 协议

- 配置是否启用对 HTTP/2 协议的支持。
- 默认：禁用 (`false`)。
- 已在 .NET Core 3.0 中引入。

| | 设置名 | 值 |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.Http2Support` | `false` - 禁用<br/>`true` - 启用 |
| **环境变量** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | `0` - 禁用<br/>`1` - 启用 |

## <a name="usesocketshttphandler"></a>UseSocketsHttpHandler

- 配置高级网络 API（如 <xref:System.Net.Http.HttpClient>）是使用 <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>，还是使用基于 [libcurl](https://curl.haxx.se/libcurl/) 的 <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> 实现。
- 默认：使用 <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`)。
- 可通过调用 <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 方法，以编程方式配置此设置。

| | 设置名 | 值 |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.UseSocketsHttpHandler` | `true` - 允许使用 <xref:System.Net.Http.SocketsHttpHandler><br/>`false` - 允许使用 <xref:System.Net.Http.HttpClientHandler> |
| **环境变量** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1` - 允许使用 <xref:System.Net.Http.SocketsHttpHandler><br/>`0` - 允许使用 <xref:System.Net.Http.HttpClientHandler> |

> [!NOTE]
> 从 .NET 5 开始，`System.Net.Http.UseSocketsHttpHandler` 设置不再可用。
