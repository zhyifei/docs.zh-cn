---
title: ".NET Framework 4.6.2 中的运行时更改 | Microsoft Docs"
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
- runtime changes, .NET Framework
- runtime changes, .NET Framework 4.6.2
- application compatibility
ms.assetid: 23bf3a87-6fa1-4b5e-b92c-a39867a06e7f
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: da809955776b5a5cd3776898ecc4c97db74ceb0e
ms.contentlocale: zh-cn
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-462"></a>.NET Framework 4.6.2 中的运行时更改
在极少数情况下，运行时更改可能影响面向以前版本的 .NET Framework 但更高版本的 .NET Framework 运行时上运行的现有应用。 他们还包括运行于不同 .NET Framework 运行时环境上的应用程序间的行为差异。 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 包括以下方面的更改：  
  
-   [核心](#Core)  
  
-   [ASP.NET 2.0](#ASP)

-   [Data](#Data)  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
-   [XML 签名和验证](#XML)  
  
<a name="Core"></a>   
## <a name="core"></a>核心  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|<xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName><br /><br /> <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory%2A?displayProperty=fullName>|在 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 中，字符是根据 Unicode 版本 8.0 进行分类。 在 .NET Framework 版本 4.5 至 4.6.1 中，Unicode 字符是根据 Unicode 版本 6.3 进行分类。<br /><br /> 此更改不会对字符比较和排序造成影响。 有关详细信息，请参阅 <xref:System.String> 类主题的“字符串和 Unicode 标准”部分。|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 和旧版 .NET Framework 中的字符分类可能不一致。 此更改主要影响切罗基语音节和西双版纳新傣文元音标记和音调标记。<br /><br /> 为了消除此更改造成的影响，应检查代码，然后删除或更改依赖硬编码 Unicode 字符分类的逻辑。|次要|  
|<xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=fullName>、<xref:System.Security.Cryptography.RSACng.ImportParameters%2A?displayProperty=fullName>、<xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey%2A?displayProperty=fullName>、<xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=fullName>|自 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 起，这些方法可以访问具有 RSA 证书非标准密钥大小的密钥。 在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 及更低版本中，尝试访问这些密钥会导致 <xref:System.Security.Cryptography.CryptographicException> 抛出。|如果在使用非标准密钥大小时有任何异常处理逻辑依赖 <xref:System.Security.Cryptography.CryptographicException>，应予以删除。|边缘|  
|<xref:System.Security.Cryptography.RSACng.VerifyHash%2A?displayProperty=fullName>|自 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 起，如果签名本身格式不正确，此方法返回 `false`。 现在，如果出现任何验证失败，此方法返回 `false`。<br /><br /> 在 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 和 4.6.1 中，如果签名本身格式不正确，此方法会抛出 <xref:System.Security.Cryptography.CryptographicException>。|如果验证失败且此方法返回 `false`，应改为执行依赖 <xref:System.Security.Cryptography.CryptographicException> 执行的任意代码。|次要|  
  
## <a name="a-nameasp--aspnet"></a><a name="ASP" />ASP.NET

|功能|更改|影响|范围| 
|-------------|------------|------------|-----------|  
| <xref:System.Web.HttpRuntime.AppDomainApopPath%2A> | 在 .NET Framework 4.6.2 中，如果检索的 <xref:System.Web.HttpRuntime.AppDomainAppPath%2A> 值包含空字符，运行时会抛出 <xref:System.NullReferenceException>。 在 .NET Framework 4.6.1 及更低版本中，运行时会抛出 <xref:System.ArgumentNullException>。  | 可以执行以下操作来响应此更改： <br/> - 如果应用程序是在 .NET Framework 4.6.2 上运行，请处理 <xref:System.NullReferenceException>。 <br /> - 升级到 .NET Framework 4.7，这将还原旧行为并抛出 <xref:System.ArgumentNullException>。 | 边缘 |

<a name="Data"></a>   
## <a name="data"></a>数据  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|Azure SQL 数据库的连接池锁定期|对于发送给已知 Azure SQL 数据库的连接打开请求，将删除连接池锁定期。|在出现暂时连接错误后随即重试连接打开请求。 有关详细信息，请参阅[缓解：池锁定期](~/docs/framework/migration-guide/mitigation-pool-blocking-period.md)。|次要|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=fullName> <br /> <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=fullName>|结合使用 NetTcp 与传输安全性和凭据类型证书时，SSL 3 协议不再是用于协商安全连接的默认协议。|在大多数情况下，应该不会对现有应用程序造成任何影响，因为 TLS 1.0 始终包含在 NetTcp 协议列表中。 所有现有客户端应该至少能够使用 TLS 1.0 来协商连接。<br /><br /> 如果必须使用 SSL 3，可以使用下面的一种配置机制，将 SSL 3 添加到协商协议列表中：<br /><br /> -   <xref:System.ServiceModel.TcpTransportSecurity?displayProperty=fullName> 属性<br />-   <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=fullName> 属性<br />-   [\<netTcpBinding>](~/docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) 的 [\<transport>](~/docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md) 部分<br />-   [\<customBinding>](~/docs/framework/configure-apps/file-schema/wcf/custombinding.md) 的 [\<sslStreamSecurity>](~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) 部分|边缘|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|<xref:System.Windows.Controls.TextBlock> 控件中父控件的 `IsEnabled` 属性|自 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 起，更改 <xref:System.Windows.Controls.TextBlock> 控件中父控件的 `IsEnabled` 属性会影响 <xref:System.Windows.Controls.TextBlock> 控件中的所有子控件（如超链接和按钮）。<br /><br /> 在 .NET Framework [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 及更低版本中，<xref:System.Windows.Controls.TextBlock> 中的控件并不总能反映 <xref:System.Windows.Controls.TextBlock> 父控件的 `IsEnabled` 属性状态。|此更改符合 <xref:System.Windows.Controls.TextBlock> 中控件的预期行为。|次要|  
|水平滚动、虚拟化和 <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName>|按与主滚动方向正交的方向自行执行虚拟化的 <xref:System.Windows.Controls.ItemsControl> 滚动操作行为已更改。|此更改为最终用户提供了更易于预测的直观体验，但可能会影响依赖水平滚动后的 <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName> 确切值的所有应用程序。 有关详细信息，请参阅[缓解：水平滚动和虚拟化](~/docs/framework/migration-guide/mitigation-horizontal-scrolling-and-virtualization.md)。|次要|  
|WPF 拼写检查器（<xref:System.Windows.Controls.SpellCheck?displayProperty=fullName> 类）|在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 控制下运行的 WPF 拼写检查存在的三个问题已在 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 中得到了解决：<br /><br /> -   在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 中，拼写检查器有时会在调用 [ISpellChecker](https://msdn.microsoft.com/library/windows/desktop/hh869767\(v=vs.85\).aspx) 或 [ISpellCheckerFactory](https://msdn.microsoft.com/library/windows/desktop/hh869770\(v=vs.85\).aspx) 方法时抛出 <xref:System.Runtime.InteropServices.COMException>。 在 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 中，这些异常已被消除。<br />-   在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 中，拼写检查器在组合词（如德语中的“Hausnummer”）中错误地标出了拼写错误。 在 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 中，拼写检查器可以正确地处理组合词。<br />-   在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 中，当应用程序通过“以其他用户身份运行”选项启动时，拼写检查器会抛出 <xref:System.UnauthorizedAccessException>。 在 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 中，这种应用场景不受支持，拼写检查器会以静默方式禁用。|这些更改提升了拼写检查器的可靠性。  应该不会对应用程序产生负面影响，除非应用程序代码依赖所抛出的异常。|边缘|  
| [DataGridCellsPanel.BringIndexIntoView](xref:System.Windows.Controls.DataGridCellsPanel.BringIndexInfoView(System.Int32)) 方法 | 在 .NET Framework 4.6.2 中，当启用列虚拟化但尚未确定列宽时，**BringIndexIntoView** 方法以异步方式执行。 不过，如果在异步操作完成之前删除列，可能会导致 <[ArgumentOutOfRangeException](xref:System.ArgumentOutOfRangeException) 抛出。<br/></br>自 .NET Framework 4.7 起，此应用场景再也不会导致异常抛出。 | 为了防止异常抛出，可以执行下列任一操作： <br/> - 升级到 .NET Framework 4.7。 <br/> - 安装 .NET Framework 4.6.2 的最新服务修补程序。 <br/> - 在对 [DataGrid.ScrollIntoView](xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)) 方法的异步响应完成前，避免删除列。 | 边缘 | 
  
<a name="XML"></a>   
## <a name="signed-xml-verification-requirements"></a>签名的 XML 验证要求  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|<xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> 和 <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName>|外部资源加载已禁用，不明确的 ID 目标被视为无效。|在许多情况下，异常都会抛出，具体包括：<br /><br /> -   使用 id 特性标识一个元素，并使用同一标识符定义另一个元素。<br />-   定义不是合法 `NCName` 值的标识符。<br />-   引用外部 URI。<br /><br /> <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A?displayProperty=fullName> 始终对以下文档返回 `false`：<br /><br /> -   使用 XPath 引用转换的文档。<br />-   使用 XSLT 引用转换的文档。<br /><br /> 开发者应检查 <xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=fullName> 和 <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> 以及派生自 <xref:System.Security.Cryptography.Xml.Transform?displayProperty=fullName> 的类型的使用情况，因为文档接收器可能无法进行处理。<br /><br /> 有关详细信息，请参阅[应用安全更新程序 3141780 后，.NET Framework 应用程序在处理包含 SignedXml 的文件时会遇到异常错误或意外失败](https://support.microsoft.com/en-us/kb/3148821)。|次要|  
  
## <a name="see-also"></a>另请参阅  
 [4.6.2 中的应用程序兼容性](~/docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)
