---
title: "使用.NET Framework 的传输层安全 (TLS) 最佳做法"
description: "介绍使用.NET Framework 使用传输层安全 (TLS) 的最佳做法"
ms.date: 03/15/2018
ms.prod: .net-framework
ms.topic: article
helpviewer_keywords:
- sending data, Internet security
- protocols, Internet security
- Network security
- network resources, Internet security
- receiving data, Internet security
- authentication [.NET Framework], Internet security
- Internet, security
- security [.NET Framework], Internet
- permissions [.NET Framework], Internet
author: blowdart
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64829eee5b21a44acb18cbec9b901d77d49cab90
ms.sourcegitcommit: 3eea47bff3201ae5d3395b0c7947806c2faca255
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2018
---
# <a name="transport-layer-security-tls-best-practices-with-the-net-framework"></a>使用.NET Framework 的传输层安全 (TLS) 最佳做法

传输层安全 (TLS) 协议是信息的行业标准旨在帮助保护通过 Internet 进行通信的私密性。 [TLS 1.2](https://tools.ietf.org/html/rfc5246)是最新的发布的标准和以前版本的基础提供安全改进。 TLS 1.2 最终将被[TLS 1.3](https://tools.ietf.org/html/draft-ietf-tls-tls13-22)。 本文提供了建议保护使用 TLS 协议的.NET Framework 应用程序。

若要确保.NET Framework 应用程序保持安全，TLS 版本应**不**进行硬编码。 .NET framework 应用程序应使用操作系统 (OS) 支持 TLS 版本。

本文档面向开发人员：

- 直接使用<xref:System.Net>Api (例如，<xref:System.Net.Http.HttpClient?displayProperty=nameWithType>和<xref:System.Net.Security.SslStream?displayProperty=nameWithType>)。
- 直接使用 WCF 客户端和服务使用<xref:System.ServiceModel?displayProperty=nameWithType>命名空间。
- 使用[Azure 云服务](https://azure.microsoft.com/services/cloud-services/)承载和运行你的应用程序的 Web 和辅助角色。 请参阅[Azure 云服务](#azure-cloud-services)部分。

我们建议您：

- 面向.NET Framework 4.7 或更高版本上你的应用。 面向.NET Framework 4.7.1 或对 WCF 应用程序的更高版本。
- 未指定 TLS 版本。 配置你的代码，以便决定使用 TLS 版本的操作系统。
- 执行全面的代码审核，以验证你在不指定的 TLS 或 SSL 版本。

当你的应用程序允许选择 TLS 版本的操作系统：

- 它会自动执行新协议添加在将来，如 TLS 1.3 优点。
- OS 阻止发现不是安全的协议。

部分[审核你的代码和进行代码更改](#audit-your-code-and-make-code-changes)介绍了审核和更新你的代码。

此文章介绍了如何启用适用于你的应用程序面向的且在上运行的.NET framework 版本的最高安全性。 当应用程序显式设置安全协议和版本时，它将 opts 超出任何其他的替代项，并 opts 退出.NET Framework 和操作系统的默认行为。 如果你希望应用才能进行协商的 TLS 1.2 连接，则将显式设置为较低的 TLS 版本将阻止 TLS 1.2 连接。

如果无法避免硬编码的协议版本，我们强烈建议您指定 TLS 1.2。 有关标识并删除 TLS 1.0 依赖项的指南，下载[解决 TLS 1.0 问题](https://www.microsoft.com/download/details.aspx?id=55266)白皮书。

WCF 支持 TLS1.0，1.1 和 1.2 作为.NET Framework 4.7 中的默认值。 从.NET Framework 4.7.1 开始，WCF 默认为操作系统配置版本。 如果应用程序显式配置与`SslProtocols.None`，当使用 NetTcp 传输时，WCF 会使用操作系统的默认设置。

你可以提问有关本文档中 GitHub 问题[传输层安全 (TLS) 的最佳做法与.NET Framework](https://github.com/dotnet/docs/issues/4675)。

## <a name="audit-your-code-and-make-code-changes"></a>审核你的代码和进行代码更改

对于 ASP.NET 应用程序中，检查`<system.web><httpRuntime targetFramework>`元素_web.config_以验证你在使用.NET Framework 目标的版本。

Windows 窗体和其他应用程序，请参阅[如何： 面向.NET Framework 版本](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)。

使用下列部分来验证你在不使用特定的 TLS 或 SSL 版本。

## <a name="if-your-app-targets-net-framework-47-or-later-versions"></a>如果你的应用面向.NET Framework 4.7 或更高版本

以下部分说明如何验证你在不使用特定的 TLS 或 SSL 版本。

### <a name="for-http-networking"></a>HTTP 网络

<xref:System.Net.ServicePointManager>使用.NET Framework 4.7 和更高版本，默认为选择的最佳安全协议和版本的操作系统。 若要获取的默认 OS 最佳选择，如果可能，未设置的值<xref:System.Net.ServicePointManager.SecurityProtocol>属性。 否则，将其设置为 <xref:System.Net.SecurityProtocolType.SystemDefault>。

面向.NET Framework 4.7 或更高版本的 HTTP 网络时，此文章的剩余部分不相关。

### <a name="for-tcp-sockets-networking"></a>有关网络的 TCP 套接字

<xref:System.Net.Security.SslStream>使用.NET Framework 4.7 和更高版本，默认为选择的最佳安全协议和版本的操作系统。 若要获取的默认 OS 最佳选择，如果可能，不使用的方法重载<xref:System.Net.Security.SslStream>它们采用显式<xref:System.Security.Authentication.SslProtocols>参数。 否则，将传递<xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>。 我们建议你不要使用<xref:System.Security.Authentication.SslProtocols.Default>; 设置`SslProtocols.Default`强制使用 SSL 3.0 /TLS 1.0 并防止 TLS 1.2。

未设置的值<xref:System.Net.ServicePointManager.SecurityProtocol>属性 （对于 HTTP 网络）。

不使用的方法重载<xref:System.Net.Security.SslStream>它们采用显式<xref:System.Security.Authentication.SslProtocols>参数 （对于 TCP 套接字网络）。 当你将重定向到.NET Framework 4.7 或更高版本应用程序时，你将以下最佳实践建议。

在面向.NET Framework 4.7 或更高版本 TCP 套接字的网络时，此主题的其余部分不相关。

<a name="wcf-tcp-cert"></a>

### <a name="for-wcf-tcp-transport-using-transport-security-with-certificate-credentials"></a>对于 WCF TCP 传输使用证书凭据的传输安全性

WCF 使用.NET Framework 的其余部分所在的相同网络堆栈。

如果你正面向 4.7.1，WCF 被配置为允许的 OS，默认情况下选择最佳的安全协议，除非显式配置：

- 在应用程序配置文件。
- **或**，应用程序中的源代码。

默认情况下，.NET Framework 4.7 及更高版本配置为使用 TLS 1.2，并允许使用 TLS 1.1 或 TLS 1.0 的连接。 配置 WCF 以允许通过配置绑定以使用选择最佳的安全协议的 OS <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>。 这可以对设置<xref:System.ServiceModel.TcpTransportSecurity.SslProtocols>。 `SslProtocols.None` 可以从访问<xref:System.ServiceModel.NetTcpSecurity.Transport>。 `NetTcpSecurity.Transport` 可以从访问<xref:System.ServiceModel.NetTcpBinding.Security>。

如果你使用自定义绑定：

- 配置 WCF 允许 OS，以通过设置选择最佳的安全协议<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols>使用<xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>。
- **或者**配置用于配置路径的协议`system.serviceModel/bindings/customBinding/binding/sslStreamSecurity:sslProtocols`。

如果你是**不**使用自定义绑定**和**正在设置 WCF 绑定使用配置，请将设置用于配置路径的协议`system.serviceModel/bindings/netTcpBinding/binding/security/transport:sslProtocols`。

### <a name="for-wcf-message-security-with-certificate-credentials"></a>使用证书凭据的 WCF 消息安全性

.NET framework 4.7 和更高版本，默认情况下的使用协议中指定<xref:System.Net.ServicePointManager.SecurityProtocol>属性。 当[AppContextSwitch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) `Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols`设置为`true`，WCF 选择最佳的协议，最多 TLS 1.0。

## <a name="if-your-app-targets-a-net-framework-version-earlier-than-47"></a>如果你的应用面向.NET Framework 版本早于 4.7

审核你的代码以验证未设置特定的 TLS 或 SSL 版本，将使用以下各节：

### <a name="for-net-framework-46---462-and-not-wfc"></a>用于.NET Framework 4.6-4.6.2 和 WFC 不

设置`DontEnableSystemDefaultTlsVersions``AppContext`切换到`false`。 请参阅[配置安全性通过 AppContext 交换机](#configuring-security-via-appcontext-switches)。

### <a name="for-wcf-using-net-framework-46---462-using-tcp-transport-security-with-certificate-credentials"></a>使用.NET Framework 4.6-4.6.2 使用证书凭据使用 TCP 传输安全的 WCF

你必须安装最新的操作系统修补程序。 请参阅[安全更新](#security-updates)。

WCF 框架会自动选择可用直到 TLS 1.2 达到的最高协议，除非您显式配置的协议版本。 有关详细信息，请参阅上一部分中[为 WCF TCP 传输使用证书凭据的传输安全性](#wcf-tcp-cert)。

### <a name="for-net-framework-35---451-and-not-wcf"></a>用于.NET Framework 3.5-4.5.1 和不 WCF

我们建议将你的应用程序升级到.NET Framework 4.7 或更高版本。 如果你不能升级，请执行以下步骤。 将来，通过在某个时间点你的应用程序可能会失败之前升级到.NET Framework 4.7 或更高版本。

设置[SchUseStrongCrypto](#schusestrongcrypto)和[SystemDefaultTlsVersions](#systemdefaulttlsversions)为 1 的注册表项。 请参阅[配置通过 Windows 注册表安全性](#configuring-security-via-the-windows-registry)。 .NET Framework 版本 3.5 支持`SchUseStrongCrypto`标志仅当显式 TLS 值传递。

如果你在.NET Framework 3.5 上运行，你需要安装热修补程序，以便 TLS 1.2 可以指定由你的程序：

| [KB3154518](https://support.microsoft.com/kb/3154518) | .NET Framework 3.5.1 在 Windows 7 SP1 和 Server 2008 R2 SP1 中包括了可靠性汇总 HR-1605-对 TLS 系统默认版本支持 |
| --- | --- |
| [KB3154519](https://support.microsoft.com/kb/3154519) | 可靠性汇总 HR-1605-TLS 系统默认版本包括在 Windows Server 2012 上的.NET Framework 3.5 的支持 |
| [KB3154520](https://support.microsoft.com/kb/3154520) | 可靠性汇总 HR 1605-Windows 8.1 和 Windows Server 2012 R2 上的.NET Framework 3.5 中包含的 TLS 系统默认版本的支持 |
| [KB3156421](https://support.microsoft.com/kb/3156421) | .NET Framework 4.5.2 和 Windows 上的 4.5.1 1605年修补程序汇总 3154521 |

### <a name="for-wcf-using-net-framework-35---452-using-tcp-transport-security-with-certificate-credentials"></a>使用.NET Framework 3.5-4.5.2 使用证书凭据使用 TCP 传输安全的 WCF

WCF framework 的这些版本进行了硬编码为使用 SSL 3.0 和 TLS 1.0 的值。 无法更改这些值。 你必须首先更新和重定目标到要使用 TLS 1.1 和 1.2 的 NET Framework 4.6 或更高版本。

## <a name="if-your-app-targets-net-framework-35"></a>如果你的应用面向.NET Framework 3.5

如果您必须显式设置而不是由.NET framework 或 OS 选取一种安全协议的安全协议，将添加`SecurityProtocolTypeExtensions`和`SslProtocolsExtension`到你的代码的枚举。 `SecurityProtocolTypeExtensions` 和`SslProtocolsExtension`包括值`Tls12`， `Tls11`，和`SystemDefault`值。 请参阅[的 TLS 系统默认版本包括在 Windows 8.1 和 Windows Server 2012 R2 上的.NET Framework 3.5 的支持](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework)。

<a name="configuring-security-via-appcontext-switches"></a>

## <a name="configuring-security-via-appcontext-switches-for-net-framework-46-or-later-versions"></a>配置安全性通过 AppContext 切换 （用于.NET Framework 4.6 或更高版本）

[AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)本节中所述的开关是相关如果你的应用面向或.NET Framework 4.6 或更高版本上的运行。 默认情况下，或通过将其显式设置，是否应为交换机`false`如有可能。 如果你想要配置安全性通过一个或两个开关，则不指定安全协议值在你的代码;因此，这样做将替代交换机。

交换机都有相同的效果所做的 HTTP 网络是否 (<xref:System.Net.ServicePointManager>) 或 TCP 套接字网络 (<xref:System.Net.Security.SslStream>)。

### <a name="switchsystemnetdontenableschusestrongcrypto"></a>Switch.System.Net.DontEnableSchUseStrongCrypto

值为`false`为`Switch.System.Net.DontEnableSchUseStrongCrypto`会导致你的应用程序以使用强加密。 值为`false`为`DontEnableSchUseStrongCrypto`使用更安全的网络协议 （TLS 1.2、 TLS 1.1 和 TLS 1.0），并阻止不安全的协议。 有关详细信息，请参阅[SCH_USE_STRONG_CRYPTO 标志](#the-schusestrongcrypto-flag)。 值为`true`禁用您的应用程序的强加密。

如果你的应用面向.NET Framework 4.6 或更高版本，此开关将默认为`false`。 这是安全默认情况下，我们建议。 如果你的应用程序在.NET Framework 4.6 上运行但面向早期版本，交换机将默认为`true`。 在这种情况下，你应显式将其设置为`false`。

`DontEnableSchUseStrongCrypto` 应仅具有的值`true`如果你需要连接到旧的服务不支持强加密，无法升级。

### <a name="switchsystemnetdontenablesystemdefaulttlsversions"></a>Switch.System.Net.DontEnableSystemDefaultTlsVersions

值为`false`为`Switch.System.Net.DontEnableSystemDefaultTlsVersions`会导致你的应用以允许操作系统选择的协议。 值为`true`会导致你的应用程序以使用.NET framework 中选取的协议。

如果你的应用面向.NET Framework 4.7 或更高版本，此开关将默认为`false`。 这是建议的安全默认值。 如果你的应用在.NET Framework 4.7 或更高版本上运行但面向早期版本，交换机将默认为`true`。 在这种情况下，你应显式将其设置为`false`。

### <a name="switchsystemservicemodeldisableusingservicepointmanagersecurityprotocols"></a>Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols

值为`false`为`Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols`使你应用程序使用中定义的值`ServicePointManager.SecurityProtocols`来提供消息安全性使用证书凭据。 值为`true`使用可用，直到 TLS1.0 达到最高的协议

面向.NET Framework 4.7 及更高版本的应用程序，此值默认为`false`。 面向.NET Framework 4.6.2 应用程序和更早版本，此值默认为`true`。

### <a name="switchsystemservicemodeldontenablesystemdefaulttlsversions"></a>Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions

值为`false`为`Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions`设置默认配置以允许操作系统选择的协议。 值为`true`将默认值设置为可用，直到 TLS1.2 达到的最高协议。

面向.NET Framework 4.7.1 和更高版本的应用程序，此值默认为`false`。 面向.NET Framework 4.7 及更早版本的应用程序，此值默认为`true`。

有关 TLS 协议的详细信息，请参阅[缓解： TLS 协议](../migration-guide/mitigation-tls-protocols.md)。 有关详细信息`AppContext`交换机，请参阅[ `<AppContextSwitchOverrides> Element` ](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)。

## <a name="configuring-security-via-the-windows-registry"></a>通过 Windows 注册表配置安全性

如果设置一个或两个`AppContext`交换机不是一个选项，您可以控制你的应用程序使用本节中所述的 Windows 注册表项具有的安全协议。 你可能不能使用一个或两`AppContext`切换如果你的应用面向.NET Framework 版本早于 4.6，或者你不能编辑配置文件。 如果你想要使用注册表中配置安全性，则不指定安全协议值在你的代码;这样做因此，将重写注册表。

注册表项的名称是类似于相应的名称`AppContext`但没有切换`DontEnable`预置的名称。 例如，`AppContext`切换`DontEnableSchUseStrongCrypto`称为注册表项[SchUseStrongCrypto](#schusestrongcrypto)。

这些密钥是在没有最新的安全修补程序的所有.NET Framework 版本中可用。 请参阅[安全更新](#security-updates)。

所有如下所述的注册表项所做的 HTTP 网络是否具有相同的效果 (<xref:System.Net.ServicePointManager>) 或 TCP 套接字网络 (<xref:System.Net.Security.SslStream>)。

### <a name="schusestrongcrypto"></a>SchUseStrongCrypto

`HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SchUseStrongCrypto`注册表项具有类型为 DWORD 值。 值为 1 会导致你的应用程序以使用强加密。 强加密使用更安全的网络协议 （TLS 1.2、 TLS 1.1 和 TLS 1.0），并阻止不安全的协议。 值为 0 禁用强加密。 有关详细信息，请参阅[SCH_USE_STRONG_CRYPTO 标志](#the-schusestrongcrypto-flag)。

如果你的应用面向.NET Framework 4.6 或更高版本，此密钥默认值为 1。 这是建议的安全默认值。 如果你的应用程序在.NET Framework 4.6 上运行但面向早期版本，该密钥将默认为 0。 在这种情况下，应显式将其值设置为 1。

如果您需要连接到旧的服务不支持强加密，无法升级，此密钥应仅具有值为 0。

### <a name="systemdefaulttlsversions"></a>SystemDefaultTlsVersions

`HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SystemDefaultTlsVersions`注册表项具有类型为 DWORD 值。 值为 1 会导致你的应用以允许操作系统选择的协议。 值为 0 会导致你的应用程序以使用.NET framework 中选取的协议。

`<VERSION>` 必须 v4.0.30319 （.NET Framework 4 及更高版本） 或 v2.0.50727 （适用于.NET Framework 3.5)。

如果你的应用面向.NET Framework 4.7 或更高版本，此密钥默认值为 1。 这是建议的安全默认值。 如果你的应用程序在.NET Framework 4.7 或更高版本上运行但面向早期版本，该密钥将默认为 0。 在这种情况下，应显式将其值设置为 1。

有关详细信息，请参阅[更新 Windows 10 版本 1511 的累积和 Windows Server 2016 Technical Preview 4: 2016 年 5 月 10，](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016)。

使用.NET framework 3.5.1 的详细信息，请参阅[支持 TLS 系统默认版本包括在 Windows 7 SP1 和 Server 2008 R2 SP1 上的.NET Framework 3.5.1](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework)。

以下_。REG_文件的注册表项和它们的变量设置为其最安全的值：

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\v2.0.50727]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\v4.0.30319]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001
```

## <a name="configuring-schannel-protocols-in-the-windows-registry"></a>在 Windows 注册表中配置 Schannel 协议

注册表可用于对客户端和/或服务器应用程序进行协商的协议细化的控制。 你的应用的网络将经历 Schannel (这是另一个名称[安全通道](https://msdn.microsoft.com/library/windows/desktop/aa380123)。 通过配置`Schannel`，你可以配置你的应用的行为。

开头`HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols`注册表项。 在该注册表项下中，你可以创建的任何子项集中`SSL 2.0`， `SSL 3.0`， `TLS 1.0`， `TLS 1.1`，和`TLS 1.2`。 在每个这些子项中，你可以创建子项`Client`和/或`Server`。 下`Client`和`Server`，你可以创建 DWORD 值`DisabledByDefault`（0 或 1） 和`Enabled`（0 或 0xFFFFFFFF）。

## <a name="the-schusestrongcrypto-flag"></a>SCH_USE_STRONG_CRYPTO 标志

启用后 (默认情况下，通过`AppContext`切换，或通过 Windows 注册表)，.NET Framework 使用`SCH_USE_STRONG_CRYPTO`标志时你的应用程序请求 TLS 安全协议。 `SCH_USE_STRONG_CRYPTO`标志可以使用默认情况下，启用`AppContext`切换，或注册表。 操作系统将传递到标志`Schannel`以指示它禁用已知弱加密算法，密码套件和可能的更好的互操作性否则启用的 TLS/SSL 协议版本。 有关详细信息，请参见:

- [安全通道](https://msdn.microsoft.com/library/windows/desktop/aa380123)
- [SCHANNEL_CRED 结构](https://msdn.microsoft.com/library/windows/desktop/aa379810)

`SCH_USE_STRONG_CRYPTO`标志还传递给`Schannel`当显式使用`Tls`(TLS 1.0) `Tls11`，或`Tls12`枚举的值<xref:System.Net.SecurityProtocolType>或<xref:System.Security.Authentication.SslProtocols>。

## <a name="security-updates"></a>安全更新

这篇文章中的最佳实践取决于正在安装新的安全更新。 这些更新包括能够使用高级的.NET Framework 4.7 和更高版本的功能。 新的安全更新是如果 （即使它面向早期版本），在.NET Framework 4.7 和更高版本上运行你的应用程序很重要。

若要更新.NET 框架，以允许操作系统选择 TLS，才能使用的最佳版本，你必须安装至少：

- [质量汇总的.NET Framework 自 2017 年 8 月预览版](https://blogs.msdn.microsoft.com/dotnet/2017/08/16/net-framework-august-2017-preview-of-quality-rollup)。
- **或者** [.NET Framework 自 2017 年 9 月安全性和质量汇总](https://blogs.msdn.microsoft.com/dotnet/2017/09/12/net-framework-september-2017-security-and-quality-rollup)。

另请参阅：

- [.NET framework 版本和依赖关系](../migration-guide/versions-and-dependencies.md)
- [如何： 确定安装了哪些.NET Framework 版本](../migration-guide/how-to-determine-which-versions-are-installed.md)。

## <a name="support-for-tls-12"></a>对 TLS 1.2 的支持

协商 TLS 1.2、 操作系统和.NET Framework 版本应用程序均需支持 TLS 1.2。

**为支持 TLS 1.2 的操作系统要求**

若要启用或重新启用 TLS 1.2 和/或 TLS 1.1 支持它们的系统上，请参阅[传输层安全 (TLS) 注册表设置](/windows-server/security/tls/tls-registry-settings)。

| **OS** | **TLS 1.2 支持** |
| --- | --- |
| Windows 10</br>Windows 2016 Server | 受支持，并且默认情况下启用。 |
| Windows 8.1</br>Windows Server 2012 R2 | 受支持，并且默认情况下启用。 |
| Windows 8.0</br>Windows Server 2012 | 受支持，并且默认情况下启用。 |
| Windows 7 SP1</br>Windows Server 2008 R2 SP1 | 支持，但默认情况下未启用。 请参阅[传输层安全 (TLS) 注册表设置](/windows-server/security/tls/tls-registry-settings)有关如何启用 TLS 1.2 的详细信息的网页。 |
| Windows Server 2008 | 支持 TLS 1.2 和 TLS 1.1 需要更新。 请参阅[更新，以在 Windows Server 2008 SP2 添加对 TLS 1.1 和 TLS 1.2 支持](https://support.microsoft.com/help/4019276/update-to-add-support-for-tls-1-1-and-tls-1-2-in-windows-server-2008-s)。 |
| Windows Vista | 不支持。 |

有关哪些 TLS/SSL 协议启用默认情况下，每个版本的 Windows 上的信息，请参阅[中 TLS/SSL (Schannel SSP) 的协议](https://msdn.microsoft.com/library/windows/desktop/mt808159)。

**使用.NET Framework 3.5 的支持 TLS 1.2 的要求**

下表显示 OS 更新，你将需要支持使用.NET Framework 3.5 的 TLS 1.2。 我们建议你将所有操作系统更新都应用。

| **OS** | **支持使用.NET Framework 3.5 的 TLS 1.2 所需的最低更新** |
| --- | --- |
| Windows 10</br>Windows 2016 Server | [为 Windows 10 版本 1511年的累积更新和 Windows Server 2016 Technical Preview 4: 2016 年 5 月 10，](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016) |
| Windows 8.1</br>Windows Server 2012 R2 | [对 TLS 系统默认版本包括在 Windows 8.1 和 Windows Server 2012 R2 上的.NET Framework 3.5 的支持](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows 8.0</br>Windows Server 2012 | [对 TLS 系统默认版本包括在 Windows Server 2012 上的.NET Framework 3.5 的支持](https://support.microsoft.com/help/3154519/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows 7 SP1</br>Windows Server 2008 R2 SP1 | [对 TLS 系统默认版本包含在.NET Framework 3.5.1 在 Windows 7 SP1 和 Server 2008 R2 SP1 的支持](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows Server 2008 | [对 TLS 系统默认版本包含在.NET Framework 2.0 SP2 在 Windows Vista SP2 和 Server 2008 SP2 上的支持](https://support.microsoft.com/help/3154517/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows Vista | 不支持 |

## <a name="azure-cloud-services"></a>Azure 云服务

如果你使用[Azure 云服务](https://azure.microsoft.com/services/cloud-services/)Web 和辅助角色承载和运行你的应用程序，有一些注意事项需要考虑到支持 TLS 1.2。

### <a name="net-framework-47-is-not-installed-on-azure-guest-os-by-default"></a>.NET framework 4.7 默认情况下未安装在 Azure 来宾 OS

安装最新的 Azure 来宾 OS 系列 5 版本 (Windows Server 2016) 中的最新版本是 4.6.2。 若要查看每个 Azure 来宾操作系统上安装的.NET Framework 的版本，请参阅[Azure 来宾 OS 版本和 SDK 兼容性矩阵](https://docs.microsoft.com/azure/cloud-services/cloud-services-guestos-update-matrix)。

如果你的应用面向在 Azure 来宾操作系统版本不可用的.NET Framework 版本，然后你需要自行安装。 请参阅[在 Azure 云服务角色上安装.NET](https://docs.microsoft.com/azure/cloud-services/cloud-services-dotnet-install-dotnet)。 如果 framework 安装需要重新启动，则服务角色可能也在进入就绪状态之前重新启动。

### <a name="azure-guest-os-registry-settings"></a>Azure 来宾 OS 注册表设置

Azure 来宾操作系统映像以便[Azure 云服务](https://azure.microsoft.com/services/cloud-services/)已`SchUseStrongCrypto`注册表项设置为 1 的值。 有关详细信息，请参阅[SchUseStrongCrypto](#schusestrongcrypto)。

设置[SystemDefaultTlsVersions](#systemdefaulttlsversions)注册表项设置为 1。 请参阅[配置通过 Windows 注册表安全性](#configuring-security-via-the-windows-registry)。
