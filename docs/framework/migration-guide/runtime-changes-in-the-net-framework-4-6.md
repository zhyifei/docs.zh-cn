---
title: ".NET Framework 4.6 中的运行时更改 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime changes, .NET Framework
- runtime changes, .NET Framework 4.6
- application compatibility
ms.assetid: 5262bcfa-6e48-416b-8972-69cb4002d386
caps.latest.revision: 34
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 77002c3d1b6553156c225b3efba9a2f29009915a
ms.contentlocale: zh-cn
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-46"></a>.NET Framework 4.6 中的运行时更改
在极少数情况下，运行时更改可能影响面向以前版本的 .NET Framework 但更高版本的 .NET Framework 运行时上运行的现有应用。 他们还包括运行于不同 .NET Framework 运行时环境上的应用程序间的行为差异。 它们包括以下区域中的更改：  
  
-   [核心](#Core)  
  
-   [Data](#Data)  
  
-   [网络](#Networking)  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
-   [安装和部署](#Setup)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [新的 64 位 JIT 编译器](#RyuJIT)  
  
<a name="Core"></a>   
## <a name="core"></a>核心  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|从 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 开始，<xref:System.Globalization.PersianCalendar> 类使用回历太阳能算法。|回历太阳能算法将产生与伊朗和阿富汗当前使用的波斯历相同的结果。 对于公历 1800 年到公历 2023 年之间的日期，它还会产生与前一种算法相同的结果。 如果 <xref:System.Globalization.PersianCalendar> 类用于执行日期转换（例如，公历日期与波斯历日期之间的转换）或用于确定某个特定年度是否为闰年，则该范围以外的日期可能会受影响。<br /><br /> 由于此更改，安装了 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 的系统的 <xref:System.Globalization.PersianCalendar.MinSupportedDateTime%2A?displayProperty=fullName> 属性值已从 0622 年 3 月 21 日更改为 0622 年 3 月 22 日。<br /><br /> 有关详细信息，请参阅 <xref:System.Globalization.PersianCalendar> 主题。|次要|  
|<xref:System.Runtime.Versioning.TargetFrameworkAttribute>|对于默认应用程序域，除非通过向 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 属性分配名称进行显式定义，否则 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 属性的值将派生自 <xref:System.Runtime.Versioning.TargetFrameworkAttribute>（如果存在）。  在 .NET Framework 的先前版本中，除非执行了大量特殊代码路径或在 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 属性中未显式指定其目标框架的情况下创建了非默认应用域，否则 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 属性的值是 `null`。<br /><br /> 对于非默认应用程序域，确定 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 属性值的方法没有更改。 如果没有值显式分配给 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 属性，则非默认应用域将从默认应用程序域继承目标框架名称。|对于默认应用程序域，<xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 可能会在之前返回 `null` 时返回非空值。 这是希望的行为。|边缘|  
|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|如果 .NET Framework 不支持系统上安装的任何证书，则传递一个 `verbose` 参数的 `True` 值会返回一个有效的字符串。 在早期版本的.NET Framework 中，尝试访问不受支持证书的公钥信息有时候会引发异常。|此方法仅用于提供信息 ；该文档说明输出在不同的 .NET Framework 版本中可能并不一定是一致的。 此更改仅影响调用 `ToString(True)` 方法且已安装 .NET Framework 不支持的证书的应用。 通过返回一个字符串而不是引发异常，此更改使该方法更具稳定性。|边缘|  
|Event Tracing for Windows (ETW) — Windows 事件跟踪 (ETW)|在 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 和 4.6.1 中，当两个事件名称只有“Start”或“Stop”后缀不同时（例如，当一个事件命名为 `LogUser`，另一个事件命名为 `LogUserStart` 时），运行时会引发 <xref:System.ArgumentException>。 在这种情况下，运行时不会构建不能发出任何日志记录的事件源。|确保不存在只有“Start”或“Stop”后缀不同的两个事件名称。<br /><br /> 从 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 开始，不再遵循此要求；运行时可以区分只有“Start”后缀不同的事件名称。|边缘|  
|反射和分布式 COM (DCOM)|反射对象可能无法再从托管代码传道至进程外客户端 以下类型会受影响：<xref:System.Reflection.Assembly>，<xref:System.Reflection.MemberInfo> 及其派生类型（包括 <xref:System.Reflection.FieldInfo>、<xref:System.Reflection.MethodInfo>、<xref:System.Type> 和 <xref:System.Reflection.TypeInfo>），<xref:System.Reflection.MethodBody>，<xref:System.Reflection.Module> 和 <xref:System.Reflection.ParameterInfo>。|调用对象的 [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707.aspx) 会返回 `E_NOINTERFACE`。|次要|  
  
<a name="Data"></a>   
## <a name="data"></a>数据  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|与解析为 `localhost` 的 SQL Server 数据库的 TCP/IP 连接|从 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 开始，连接尝试会失败，并显示错误“在与 SQL Server 建立连接时出现网络相关的错误或特定于实例的错误。 未找到或无法访问服务器。 请验证实例名称是否正确，SQL Server 是否已配置为允许远程连接。 （提供程序：SQL 网络接口，错误：26 - 定位指定的服务器/实例时出错）”|在 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 中，此问题已得到解决，并已恢复以前的行为。 若要连接到会解析为 `localhost` 的 SQL Server 数据库，请升级到 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]。|次要|  
  
<a name="Networking"></a>   
## <a name="networking"></a>网络  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|<xref:System.Net.Mime.ContentDisposition?displayProperty=fullName> 类中的日期和时间值。|若要符合 [RFC822](http://www.ietf.org/rfc/rfc0822.txt) 和 [RFC2822](http://www.ietf.org/rfc/rfc2822.txt)，格式化的日期和时间值现在是具有两位数的小时数。 以前，它在上午 10:00 之前的值为一位数字的小时数。|此更改将影响以下使用方案：<br /><br /> -   在各个 .NET Framework 版本间比较序列化的 <xref:System.Net.Mime.ContentDisposition> 对象的长度或哈希代码。<br />-   在各个 .NET Framework 版本间比较 <xref:System.Net.Mime.ContentDisposition.ToString%2A> 方法的返回值或 <xref:System.Net.Mime.ContentDisposition> 日期和时间属性值的字符串表示形式。|次要|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|使用带有 SSL 安全和证书身份验证的 NETTCP 的 WCF 服务|.NET Framework 4.6 将 TLS 1.1 和 TLS 1.2 添加到 WCF SSL 默认协议列表。 客户端和服务器计算机都安装了 .NET Framework 4.6 或更高版本时，TLS 1.2 用于协商。|TLS 1.2 不支持 MD5 证书身份验证。 因此，如果客户使用 MD5 证书，WCF 客户端将无法连接到 WCF 服务。 有关详细信息，请参阅[缓解：WCF 服务和证书身份验证](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md)。|次要|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|多监视器方案中的窗口呈现|当一个窗口超出多监视器方案中的某个显示屏时，会不经剪辑就呈现整个窗口。|请参阅[缓解：WPF 窗口呈现](../../../docs/framework/migration-guide/mitigation-wpf-window-rendering.md)。|次要|  
|支持 WPF 文本的控件上的拼写检查器|在 Windows 10 上运行时，拼写检查器可能不会工作，因为平台拼写检查功能仅适用于输入语言列表中存在的语言。|在 Windows 10 中，可用键盘列表中增加了一种语言，Windows 自动下载并安装相应的功能按需 (FOD) 包，以提供拼写检查功能。 通过将语言添加到输入语言列表，将支持拼写检查器。|次要|  
  
<a name="Setup"></a>   
## <a name="setup-and-deployment"></a>安装和部署  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|产品版本控制|产品版本控制已从早期版本的 .NET Framework 进行了更改，特别是 .NET Framework 4、4.5、4.5.1 和 4.5.2。 有关详细信息，请参阅[缓解：产品版本控制](../../../docs/framework/migration-guide/mitigation-product-versioning.md)。|请参阅[缓解：产品版本控制](../../../docs/framework/migration-guide/mitigation-product-versioning.md)。|中等|  
  
<a name="ClickOnce"></a>   
## <a name="clickonce"></a>ClickOnce  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|通过 ClickOnce 使用 SHA-256 代码签名证书发布的应用。|面向 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 或早期版本的 ClickOnce 应用均采用 SHA-256 证书签名，在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 或更高版本上不再依赖运行时。|以前，对面向带 SHA-256 证书的 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 或早期版本的 ClickOnce 应用签名，需要在目标系统上安装 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 或更高版本。 如果没有安装，将导致错误。 此更改移除了该依赖性，并允许将 SHA-256 证书用于为面向 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 或早期版本的 ClickOnce 应用签名。|次要|  
  
<a name="RyuJIT"></a>   
## <a name="the-new-64-bit-jit-compiler"></a>新的 64 位 JIT 编译器  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|64 位 JIT 编译|从 .NET Framework 4.6 开始，新的 64 位 JIT 编译器用于实时编译。 此更改不会影响 32 位 JIT 编译器。|在某些情况下，会引发意外异常，或观察到不同行为，比如使用 32 位编译器或旧的 64 位 JIT 编译器运行应用时。 **注意：**所有这些问题已在随 .NET Framework 4.6.2 发布的新 64 位编译器中得到解决。 大多数问题也已在 Windows 更新随附的 .NET Framework 4.6 和 4.6.1 的服务版本中得到解决。 <br /><br /> 有关详细信息，请参阅[缓解：新的 64 位 JIT 编译器](../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)。|边缘|  
|异常处理（从 `try` 区域返回）|与旧版 JIT64 实时编译器不同，新版 64 位 JIT 编译器不允许在 `try` 区域中使用 IL `ret` 指令。|ECMA-335 规范不允许从 `try` 区域返回，并且没有已知的托管编译器会生成此类 IL。 但是，如果由反射发出生成，则 JIT64 编译器执行此类 IL。<br /><br /> 如果应用程序生成的 IL 在 `try` 区域中包含 `ret` 操作码，则可以：<br /><br /> -   面向 .NET Framework 4.5 或将 [\<useLegacyJIT>](../../../docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md) 元素添加到你的应用程序配置文件，使用旧的 JIT 编译器并避免更改。<br />-   将生成的 IL 更新为在 `try` 区域之后返回。<br />-|边缘|
