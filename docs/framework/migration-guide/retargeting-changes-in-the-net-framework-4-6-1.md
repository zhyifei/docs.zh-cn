---
title: ".NET Framework 4.6.1 中的重定目标更改 | Microsoft Docs"
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
- retargeting changes, .NET Framework
- retargeting changes, .NET Framework 4.6.1
- application compatibility
ms.assetid: 411ad548-30fa-43da-8716-10eccfc839e6
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0adc4a6cae566b6a15c5fa492620abb74b47335b
ms.contentlocale: zh-cn
ms.lasthandoff: 04/18/2017

---
# <a name="retargeting-changes-in-the-net-framework-461"></a>.NET Framework 4.6.1 中的重定目标更改
在极少数情况下，重定目标更改可能影响那些编译为面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的应用。 除非另行指定，否则这些更改不会影响面向以前版本的 .NET Framework 但在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 下运行的二进制文件。  
  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 包括以下方面的重定目标更改：  
  
-   [核心](#Core)  
  
-   [代码协定](#Contracts)  
  
-   [Windows Communication Foundation](#WCF)  
  
-   [Windows 窗体](#WinForms)  
  
<a name="Core"></a>   
## <a name="core"></a>核心  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|<xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=fullName>|对于面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 及更高版本的应用，在通过重载 <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=fullName> 方法创建的 <xref:System.IO.Compression.ZipArchiveEntry> 对象的 <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A> 属性中，路径分隔符已从反斜杠（“\\”）更改为正斜杠（“/”）。|该更改使 .NET 实现遵循 [.ZIP 文件格式规范](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT)的 4.4.17.1 部分，还允许 .ZIP 存档在非 Windows 系统上进行解压缩。<br /><br /> 不过，面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 及更高版本的应用可以选择退出此行为。 有关详细信息，请参阅[缓解：ZipArchiveEntry.FullName 路径分隔符](../../../docs/framework/migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md)。|边缘|  
  
<a name="Contracts"></a>   
## <a name="code-contracts"></a>代码协定  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|<xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=fullName> 和 <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=fullName>，以及对 <xref:System.String.IsNullOrEmpty%2A?displayProperty=fullName> 的调用|对于面向 .NET Framework 4.6.1 的应用，重写器会发出编译器警告 CC1036：“检测到对方法‘System.String.IsNullOrWhiteSpace(System.String)’的调用，方法中未带 [Pure]...”|这是编译器警告，不是编译器错误。<br /><br /> 此行为在 [GitHub 问题 #339](https://github.com/Microsoft/CodeContracts/issues/339) 中已得到解决。 若要去除此警告，可以从 [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md) 下载并编译代码协定工具的已更新版本的源代码。 可在页面底部找到下载信息。|次要|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation"></a>Windows Communication Foundation  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName><br /><br /> （<xref:System.IdentityModel.Claims> 命名空间）|在面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的应用中，如果从其 SAN 字段中具有多个 DNS 条目的证书初始化 X509 声明集，<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A> 方法会尝试将 `claimType` 自变量与所有 DNS 条目进行匹配。<br /><br /> 对于面向 .NET Framework 先前版本的应用，<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A> 方法会尝试仅将 `claimType` 自变量与最后一个 DNS 条目进行匹配。|此更改会影响面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的所有应用。 面向 .NET framework 先前版本的应用不受影响。<br /><br /> 不过，面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的应用可以选择退出此行为。 此外，面向 .NET Framework 先前版本但在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 下运行的应用可以选择加入此行为。 有关详细信息，请参阅[缓解：X509CertificateClaimSet.FindClaims 方法](../../../docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md)。|次要|  
  
<a name="WinForms"></a>   
## <a name="windows-forms"></a>Windows 窗体  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|<xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> 方法（<xref:System.Windows.Forms> 命名空间）|在面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的 Windows 窗体应用中，如果 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> 实现满足以下要求，则在调用 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> 方法时，自定义 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> 实现可以安全地筛选消息：<br /><br /> <ul><li>执行下列一项或两项操作：<br /><br /> <ul><li>通过调用 <xref:System.Windows.Forms.Application.AddMessageFilter%2A> 方法添加消息筛选器。</li><li>通过调用 <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> 方法删除消息筛选器。 方法。</li></ul></li><li>**以及**通过调用 <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName> 方法抽取消息。</li></ul><br /> 对于面向 .NET Framework 先前版本的 Windows 窗体应用中的此类实现，调用 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> 方法时，在某些情况下会引发 <xref:System.IndexOutOfRangeException> 异常|此更改会影响面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的所有应用。 面向 .NET framework 先前版本的应用不受影响。<br /><br /> 不过，面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的应用可以选择退出此行为。 此外，面向 .NET Framework 先前版本但在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 下运行的应用可以选择加入此行为。 有关详细信息，请参阅[缓解：自定义 IMessageFilter.PreFilterMessage 实现](../../../docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)。|边缘|  
  
## <a name="see-also"></a>另请参阅  
 [4.6.1 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)
