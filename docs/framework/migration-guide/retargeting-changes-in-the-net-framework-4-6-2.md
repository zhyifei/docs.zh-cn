---
title: ".NET Framework 4.6.2 中的重定目标更改 | Microsoft Docs"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes, .NET Framework
- retargeting changes, .NET Framework 4.6.2
- application compatibility
ms.assetid: 76dc6849-8210-4e41-8731-20828c98b282
caps.latest.revision: 26
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 229ccf3fa4ff1029334641da350cfd040e4b286e
ms.lasthandoff: 04/18/2017

---
# <a name="retargeting-changes-in-the-net-framework-462"></a>.NET Framework 4.6.2 中的重定目标更改
在极少数情况下，重定目标更改可能影响那些编译为面向 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 的应用。 这些更改不会影响定位旧版 .NET Framework 但在版本 4.6.2 控制下运行的二进制文件。 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 包括以下方面的重定目标更改：  
  
-   [核心](#Core)  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows 窗体](#WinForms)  
  
 下表中的“范围”列指定每个更改的基数：  
  
-   主要。 显著的更改，可影响大量应用或需要修改大量代码。 请注意，没有重定目标更改归入此类别。  
  
-   次要。 影响少量应用或需要修改少量代码的更改。  
  
-   边缘。 仅在少数非常特定的情况下影响应用的更改。  
  
-   透明。 对应用的开发人员或用户没有明显影响的更改。 不需要由于此更改而修改应用。  
  
<a name="Core"></a>   
## <a name="core"></a>核心  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|长路径支持|自定位 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 的应用程序起，支持长路径（最多可包含 32000 个字符），260（或 `MAX_PATH`）个字符的路径长度上限已被撤消。|对于定位 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 的应用程序，以前抛出 <xref:System.IO.PathTooLongException> 的代码路径再也不会抛出异常。 有关详细信息，请参阅[缓解：长路径支持](~/docs/framework/migration-guide/mitigation-long-path-support.md)。|次要|  
|路径规范化|自定位 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 的应用程序起，路径规范化的方式已更改为以操作系统为准，以便更好地访问 DOS 设备路径。|借助这些更改，可以访问以前不受支持的有效设备路径。 有关详细信息，请参阅[缓解：路径规范化](~/docs/framework/migration-guide/mitigation-path-normalization.md)。|次要|  
|<xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> 和 <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName>|自定位 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 的应用程序起，为了支持以前不受支持的路径，执行了大量更改（无论是在长度方面还是在格式方面）。 特别是，能够更加准确地检查驱动器分隔符语法（冒号）的用法是否正确。|这些更改屏蔽了这两种方法以前支持的一些 URI 路径。 有关详细信息，请参阅[缓解：路径冒号检查](~/docs/framework/migration-guide/mitigation-path-colon-checks.md)。|边缘|  
|<xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> 构造函数|自 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 起，通过调用 <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> 方法创建的 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> 属性是一个新 <xref:System.Security.Claims.ClaimsIdentity> 实例。 在旧版 .NET Framework 中，<xref:System.Security.Claims.ClaimsIdentity.Actor%2A> 是现有引用。|在某些情况下，比较 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> 属性与构造函数的 <xref:System.Security.Principal.IIdentity> 的 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> 属性可能会返回不同的结果。<br /><br /> 有关详细信息，请参阅[缓解：ClaimsIdentity 构造函数](~/docs/framework/migration-guide/mitigation-claimsidentity-constructor.md)。|边缘|  
|<xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor%2A?displayProperty=fullName>|自定位 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 的应用程序起，<xref:System.Security.Cryptography.AesCryptoServiceProvider> 解密器提供了可重用的转换。   调用<xref:System.Security.Cryptography.ICryptoTransform.TransformFinalBlock%2A> 后，此转换将重新初始化，以便可以重用。<br /><br /> 对于定位旧版 .NET framework 的应用程序，在调用 <xref:System.Security.Cryptography.ICryptoTransform.TransformFinalBlock%2A> 后，尝试通过调用 <xref:System.Security.Cryptography.ICryptoTransform.TransformBlock%2A> 重用解密器会导致 <xref:System.Security.Cryptography.CryptographicException> 抛出或数据损坏。|由于这是预期行为，因此造成的影响应该是最少的。<br /><br /> 对于依赖旧行为的应用程序，可以在应用程序配置文件的 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中添加下面的配置设置，从而选择禁用此更改：<br /><br /> `<runtime>    <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true"/> </runtime>`<br /><br /> 此外，对于定位旧版 .NET framework，但在 .NET framework [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 及更高版本控制下运行的应用程序，可以在应用程序配置文件的 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中添加下面的配置设置，从而选择启用此更改：<br /><br /> `<runtime>    <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false"/> </runtime>`|次要|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|使用 CNG 对存储的证书的 WCF 传输安全支持|自定位 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 的应用程序起，WCF 传输安全性支持使用 Windows 加密库 (CNG) 存储的证书。 此支持仅限于将证书与指数长度不超过 32 位的公钥结合使用。 应用程序面向 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 时，此功能默认启用。<br /><br /> 在旧版 .NET framework 中，尝试将 X509 证书与 CSG 密钥存储提供程序结合使用会导致异常抛出。|对于定位 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 及更低版本，但在 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 上运行的应用程序，可以在 app.config 或 web.config 文件的 runtime 部分中添加下面的代码行，从而启用对 CNG 证书的支持。<br /><br /> `<AppContextSwitchOverrides     value="Switch.System.ServiceModel.DisableCngCertificates=false" />`<br /><br /> 也可以使用以下代码以编程方式完成此操作：<br /><br /> `private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificate"; AppContext.SetSwitch(disableCngCertificates, false);`<br /><br /> `Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates" AppContext.SetSwitch(disableCngCertificates, False)`<br /><br /> 请注意，鉴于有此更改，将不再执行任何依赖无法尝试使用 CNG 证书启动安全通信的异常处理代码。|次要|  
  
<a name="WinForms"></a>   
## <a name="windows-forms"></a>Windows 窗体  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|<xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>、`System.ComponentModel.EventDescriptor.Equals` 和 `System.ComponentModel.PropertyDescriptor.Equals`|自定位 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 的应用程序起，基类 <xref:System.ComponentModel.MemberDescriptor.Equals%2A> 方法的实现代码已更改。|由于相等性测试结果现在符合预期，因此这一更改应该不会产生什么影响。<br /><br /> 不过，对于定位 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 且依赖旧行为的应用程序，可以选择禁用此更改。 同样，对于定位旧版 .NET Framework，但在 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 控制下运行的应用程序，可以选择启用此更改。 有关详细信息，请参阅[缓解：MemberDescriptor.Equals](~/docs/framework/migration-guide/mitigation-memberdescriptor-equals.md)。|边缘|  
  
## <a name="see-also"></a>另请参阅  
 [4.6.2 中的应用程序兼容性](~/docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)
