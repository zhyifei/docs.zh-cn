---
title: ".NET Framework 4.6.1 中的重定目标更改 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 411ad548-30fa-43da-8716-10eccfc839e6
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# .NET Framework 4.6.1 中的重定目标更改
在极少数情况下，重定目标更改可能影响那些编译为面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的应用。 除非另行指定，否则这些更改不会影响面向以前版本的 .NET Framework 但在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 下运行的二进制文件。  
  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 包括以下方面的重定目标更改：  
  
-   [Windows Communication Foundation](#WCF)  
  
-   [Windows 窗体](#WinForms)  
  
<a name="WCF"></a>   
## Windows Communication Foundation  
  
|功能|更改|影响|范围|  
|--------|--------|--------|--------|  
|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName><br /><br /> （<xref:System.IdentityModel.Claims> 命名空间）|在面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的应用中，如果 X509 声明集从 SAN 字段拥有多个 DNS 条目的证书初始化，<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A> 方法会尝试将 `claimType` 参数与所有 DNS 条目进行匹配。<br /><br /> 对于面向 .NET Framework 先前版本的应用，<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A> 方法尝试仅将 `claimType` 参数与最后一个 DNS 条目进行匹配。|此更改影响面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的所有应用。 面向 .NET framework 先前版本的应用不受影响。<br /><br /> 但是，可以为面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的应用选择退出此行为。 此外，可以为面向 .NET framework 先前版本但在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 下运行的应用选择加入此行为。 有关更多信息，请参见[缓解操作：X509CertificiateClaimSet.FindClaims 方法](../../../docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md)。|次要|  
  
<a name="WinForms"></a>   
## Windows 窗体  
  
|功能|更改|影响|范围|  
|--------|--------|--------|--------|  
|<xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> 方法（<xref:System.Windows.Forms> 命名空间）|在面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的 Windows 窗体应用中，如果自定义 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> 实现满足以下要求，那么在调用 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> 方法时，该 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> 实现可以安全地筛选消息：<br /><br /> <ul><li>执行下列一项或两项操作：<br /><br /> <ul><li>通过调用 <xref:System.Windows.Forms.Application.AddMessageFilter%2A> 方法添加消息筛选器。</li><li>通过调用 <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> 方法删除消息筛选器。 方法。</li></ul></li><li>**以及**通过调用 <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName> 方法抽取消息。</li></ul><br /> 对于面向 .NET framework 先前版本的 Windows 窗体应用中的此类实现，调用 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> 方法时在某些情况下会引发 <xref:System.IndexOutOfRangeException> 异常|此更改影响面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的所有应用。 面向 .NET framework 先前版本的应用不受影响。<br /><br /> 但是，可以为面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的应用选择退出此行为。 此外，可以为面向 .NET framework 先前版本但在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 下运行的应用选择加入此行为。 有关详细信息，请参阅[缓解操作：自定义 IMessageFilter.PreFilterMessage 实现](../../../docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)。|边缘|  
  
## 请参阅  
 [4.6.1 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)