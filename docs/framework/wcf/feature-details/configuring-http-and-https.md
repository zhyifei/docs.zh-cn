---
title: 配置 HTTP 和 HTTPS 的 WCF
ms.date: 04/08/2019
helpviewer_keywords:
- configuring HTTP [WCF]
ms.assetid: b0c29a86-bc0c-41b3-bc1e-4eb5bb5714d4
ms.openlocfilehash: 86705a4f8daa327c442ac6c53c9b44c5b5c5c2ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857358"
---
# <a name="configuring-http-and-https"></a>配置 HTTP 和 HTTPS

WCF 服务和客户端可以通过 HTTP 和 HTTPS 通信。 通过使用 Internet Information Services (IIS) 或命令行工具可以配置 HTTP/HTTPS 设置。 当某个 WCF 服务承载于 IIS 之下时，可以在 IIS 中配置 HTTP 或 HTTPS 设置（使用 inetmgr.exe 工具）。 如果 WCF 服务是自承载的，则可使用命令行工具配置 HTTP 或 HTTPS 设置。

至少，你想要配置 URL 注册，并将使用你的服务的 url 添加防火墙例外。 您可以使用 Netsh.exe 工具配置这些设置。

## <a name="configuring-namespace-reservations"></a>配置命名空间保留

命名空间预留将 HTTP URL 命名空间的一部分的权限分配给特定的用户组。 预留提供给这些用户创建用于侦听命名空间的相应部分的服务的权限。 保留是 URL 前缀，这意味着保留涵盖保留路径的所有子路径。 命名空间预留允许以两种方式使用通配符。 HTTP Server API 文档描述[涉及通配符的命名空间声明之间的解析顺序](/windows/desktop/Http/routing-incoming-requests)。

运行的应用程序可以创建一个类似请求来添加命名空间注册。 注册和预留会竞争命名空间的某些部分。 保留可能优先于给定的解析顺序根据注册[涉及通配符的命名空间声明之间的解析顺序](/windows/desktop/Http/routing-incoming-requests)。 在此情况下，预留会阻止运行的应用程序接收请求。

以下示例使用 Netsh.exe 工具：

```console
netsh http add urlacl url=http://+:80/MyUri user=DOMAIN\user
```

此命令将添加 URL 保留项指定的 URL 命名空间的域 \ 用户帐户。 使用 netsh 命令的详细信息，请键入`netsh http add urlacl /?`在命令提示符，然后按 Enter 键。

## <a name="configuring-a-firewall-exception"></a>配置防火墙例外

当自承载通过 HTTP 进行通信的 WCF 服务时，必须向防火墙配置添加一个例外，以允许使用特定 URL 的入站连接。

## <a name="configuring-ssl-certificates"></a>配置 SSL 证书

安全套接字层 (SSL) 协议在客户端和服务器上使用证书来存储加密密钥。 在建立连接时，服务器会提供其 SSL 证书，以便客户端验证服务器标识。 服务器还可以从客户端请求证书以提供连接双方的相互身份验证。

证书将根据连接的 IP 地址和端口号存储在一个中央存储区中。 特殊的 IP 地址 0.0.0.0 可以与本地计算机的任何 IP 地址相匹配。 请注意证书存储区不会区分基于路径的 Url。 即使服务的 URL 中的路径不同，带有相同 IP 地址和端口组合的服务也必须共享证书。

有关分步说明，请参阅[如何：使用 SSL 证书配置端口](how-to-configure-a-port-with-an-ssl-certificate.md)。

## <a name="configuring-the-ip-listen-list"></a>配置 IP 侦听列表

在用户注册一个 URL 之后，HTTP 服务器 API 只绑定到一个 IP 地址和端口。 默认情况下，对于计算机的所有 IP 地址，HTTP 服务器 API 将绑定到所注册的 URL 中的端口。 如果不使用 HTTP 服务器 API 的应用程序先前已经绑定到该 IP 地址和端口组合，则会发生冲突。 IP 侦听列表允许 WCF 服务与某些计算机的 IP 地址使用的端口的应用程序共存。 如果 IP 侦听列表包含任何项，则 HTTP 服务器 API 只绑定到该列表指定的那些 IP 地址。 修改 IP 侦听列表需要管理特权。

使用 netsh 工具修改 IP 侦听列表，如下面的示例中所示：

```console
netsh http add iplisten ipaddress=0.0.0.0:8000
```

## <a name="other-configuration-settings"></a>其他配置设置

使用 <xref:System.ServiceModel.WSDualHttpBinding> 时，客户端连接使用与命名空间预留和 Windows 防火墙兼容的默认设置。 如果选择自定义双向连接的客户端基址，则还必须配置这些客户端上的 HTTP 设置以与新地址相匹配。

HTTP 服务器 API 具有不可通过 HttpCfg 某些高级的配置设置。 这些设置保留在注册表中并应用于在使用 HTTP 服务器 API 的系统上运行的所有应用程序。 有关这些设置的信息，请参阅[用于 IIS 的 Http.sys 注册表设置](https://support.microsoft.com/en-us/help/820129/http-sys-registry-settings-for-windows)。 大多数用户无需更改这些设置。

## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.WSDualHttpBinding>
- [如何：使用 SSL 证书配置端口](how-to-configure-a-port-with-an-ssl-certificate.md)
