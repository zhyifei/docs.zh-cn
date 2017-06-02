---
title: ".NET Framework 4.6 中的重定目标更改 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fa849255-f90f-4bf1-b0ff-b173c12110d7
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# .NET Framework 4.6 中的重定目标更改
在极少数情况下，重定目标更改可能影响那些编译为面向 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 的应用。 除非另行指定，否则这些更改不会影响面向以前版本的 .NET Framework 但在 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 下运行的二进制文件。  
  
 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 包括以下方面的重定目标更改：  
  
-   [ASP.NET](#ASP)  
  
-   [网络](#Net)  
  
-   [Windows Communication Foundation \(WCF\)](#WCF)  
  
-   [Windows 窗体](#WinForms)  
  
-   [Windows Presentation Foundation \(WPF\)](#WPF)  
  
-   [XML](#XML)  
  
<a name="ASP"></a>   
## ASP.NET  
  
|功能|更改|影响|范围|  
|--------|--------|--------|--------|  
|具有 <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName> 的 `tagKey` 值的 <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName>|为符合 HTML 标准，<xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName> 方法现在 HTML 响应中将 <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName> 呈现为非结束标记。|BR 标记现在会生成一个换行符。 以前，它会生成 2 个换行符。<br /><br /> 依赖于 `<BR>` 标记来生成 2 个换行符的应用可以通过向具有 <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName> 参数的 <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName> 方法添加额外调用，来还原以前的行为。|次要|  
  
<a name="Net"></a>   
## 网络  
  
|功能|更改|影响|范围|  
|--------|--------|--------|--------|  
|<xref:System.Net.ServicePointManager?displayProperty=fullName> 和 <xref:System.Net.Security.SslStream?displayProperty=fullName>|从面向 .NET Framework 4.6 的应用开始，<xref:System.Net.ServicePointManager?displayProperty=fullName> 和 <xref:System.Net.Security.SslStream?displayProperty=fullName> 类可以使用以下三种协议之一：Tls1.0、Tls1.1 或 Tls 1.2。<br /><br /> 面向以前版本的 .NET Framework 的应用即使在 NET Framework 4.6 上运行也不会受到影响。|此更改会影响面向 .NET Framework 4.6 并使用 SSL 与 HTTPS 服务器或与使用以下任何类型的套接字对话的任何应用：<xref:System.Net.Http.HttpClient>、<xref:System.Net.HttpWebRequest><xref:System.Net.FtpWebRequest>、<xref:System.Net.Mail.SmtpClient> 和 <xref:System.Net.Security.SslStream>。  有关详细信息，请参阅[缓解：TLS 协议](../../../docs/framework/migration-guide/mitigation-tls-protocols.md)。|次要|  
  
<a name="WCF"></a>   
## Windows Communication Foundation \(WCF\)  
  
|功能|更改|影响|范围|  
|--------|--------|--------|--------|  
|<xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%2A?displayProperty=fullName>|调用具有 `null` `authorizationPolicies` 参数的 <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> 所返回的 <xref:System.IdentityModel.Policy.AuthorizationContext> 实现更改了其在 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 中的实现。|在极少数情况下，使用自定义身份验证的 WCF 应用可能会看到行为差异。 如果需要此旧行为，请参阅[缓解：默认 AuthorizationContext](../../../docs/framework/migration-guide/mitigation-default-authorizationcontext.md)。|次要|  
  
<a name="WinForms"></a>   
## Windows 窗体  
  
|功能|更改|影响|范围|  
|--------|--------|--------|--------|  
|<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName>|从面向 .NET Framework 4.6 的应用开始，<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> 方法成功将带 PNG 帧的图标转换为 <xref:System.Drawing.Bitmap> 对象。<br /><br /> 在面向 .NET Framework 4.5.2 和更早版本的应用中，<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> 方法在 <xref:System.Drawing.Icon> 对象具有 PNG 帧时引发 <xref:System.ArgumentOutOfRangeException> 异常。|此更改会影响以下应用：重新编译为面向 .NET Framework 4.6 的应用，以及对在 <xref:System.Drawing.Icon> 对象具有 PNG 帧时引发的 <xref:System.ArgumentOutOfRangeException> 异常提供特殊处理的应用。 如果不需要此行为，配置开关可还原以前的行为。 有关详细信息，请参阅[缓解操作：图标对象中的 PNG 帧](../../../docs/framework/migration-guide/mitigation-png-frames-in-icon-objects.md)。|次要|  
  
<a name="WPF"></a>   
## Windows Presentation Foundation \(WPF\)  
  
|功能|更改|影响|范围|  
|--------|--------|--------|--------|  
|高 DPI 处舍入的布局|边距舍入的方式以及边框和边框内的背景已更改。|WPF 控件的布局可能稍有变化。 有关详细信息，请参阅[缓解：WPF 布局](../../../docs/framework/migration-guide/mitigation-wpf-layout.md)。|次要|  
  
<a name="XML"></a>   
## XML  
  
|功能|更改|影响|范围|  
|--------|--------|--------|--------|  
|XSD 架构验证|从 .NET Framework 4.6 开始，如果使用复合键且有一个键为空，则 XSD 架构验证将检测是否违反唯一约束。|请参见[缓解：XML 架构验证](../../../docs/framework/migration-guide/mitigation-xml-schema-validation.md)|次要|  
|<xref:System.Xml.XmlWriter>|对于面向 .NET Framework 4.5.2 或以前的版本的应用程序，使用异常回退处理编写无效的代理项对并不会总是引发异常。<br /><br /> 对于面向 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 的应用程序，尝试编写无效的代理项对会引发 <xref:System.ArgumentException> 异常。|重新编译以面向 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 的应用与编写无效代理项的应用可能在之前没有引发异常时引发异常。|边缘|