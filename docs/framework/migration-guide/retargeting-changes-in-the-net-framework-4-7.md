---
title: ".NET Framework 4.7 中的重定目标更改 | Microsoft Docs"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes,.NET Framework
- retargeting changes,.NET Framework 4.7
- application compatibility
ms.assetid: d98bf1e3-0017-4933-8e7b-191ac3542fcc
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: fccd83571b47e3c2a6f995893c6260ae91eae517
ms.openlocfilehash: 53c3bc41e319fe122605993d4013e6f04832c89c
ms.contentlocale: zh-cn
ms.lasthandoff: 05/22/2017

---
# <a name="retargeting-changes-in-the-net-framework-47"></a>.NET Framework 4.7 中的重定目标更改

在极少数情况下，重定目标更改可能会影响重新编译为定位 .NET Framework 4.7 的应用程序。 这些更改不会影响定位旧版 .NET Framework，但在版本 4.7 控制下运行的二进制文件。 NET Framework 4.7 在以下几个领域进行了重定目标更改：  

-   [核心](#Core)  
-   [ASP.NET 2.0](#asp) 
-   [Windows Communication Foundation (WCF)](#WCF)  
-   [Windows Presentation Foundation (WPF)](#WPF)
 
 下表中的“范围”列指定每个更改的基数：  
  
-   主要。 显著的更改，可影响大量应用或需要修改大量代码。 请注意，没有重定目标更改归入此类别。  
  
-   次要。 影响少量应用或需要修改少量代码的更改。  
  
-   边缘。 仅在少数非常特定的情况下影响应用的更改。  
  
-   透明。 对应用的开发人员或用户没有明显影响的更改。 不需要由于此更改而修改应用。  
  
## <a name="a-namecore--core"></a><a name="Core" />Core

| 功能 | 更改 | 影响 | 范围 |
|----|----|----|----|
|<xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> | 对于定位 .NET Framework 4.6.2 及更低版本的应用程序，分配给此属性的值应为 <xref:System.IntPtr>，用于表示 HWND 值在内存中驻留的指定位置。<br/></br>自定位 .NET Framework 4.7 的应用程序起，Windows 窗体应用程序可以使用如下代码设置此属性的值： <br/><br/>` cspParameters.ParentWindowHandle = form.Handle; ` | 对于这种行为变化对其造成不便的应用程序，可以选择禁用这一新行为。 同样，对于定位旧版 .NET Framework，但在 .NET Framework 4.7 上运行的应用程序，可以选择启用这一新行为。 有关详细信息，请参阅[缓解：应向 CspParameters.ParentWindowHandle 分配 HWND](../../../docs/framework/migration-guide/mitigation-cspparameters-parentwindowhandle-expects-an-hwnd.md)。 | 次要 |
| 使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 进行序列化 | 自定位 .NET Framework 4.7 的应用程序起，使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 对控制字符进行序列化现与 ECMAScript V6 和 V8 兼容。 | 此更改符合 ECMAScript 标准，因此应该不会产生什么影响。 如果有影响，可以使用兼容性开关还原旧行为。 有关详细信息，请参阅[缓解：使用 DataContractJsonSerializer 对控制字符进行序列化](../../../docs/framework/migration-guide/mitigation-serialization-control-characters.md)  | 边缘 |

## <a name="a-nameasp--aspnet"></a><a name="asp" />ASP.NET

| 功能  |更改  |影响 | 范围 | 
---------|---------|---------|-----|
每个会话的限制并发请求数 | 在 .NET Framework 4.6.2 及更低版本中，ASP.NET 依序执行具有相同 <xref:System.Web.SessionState.HttpSessionState.SessionID%2A> 的请求，并且 ASP.NET 始终默认通过 Cookie 发出<xref:System.Web.SessionState.HttpSessionState.SessionID%2A>。 如果页面加载时间过长，在浏览器中按 <kbd>F5</kbd> 会大大降低服务器性能。<br/><br/>自 .NET Framework 4.7 起，计数器会跟踪已排入队列的请求，并在它们超出指定限制时终止请求。 默认值为 50。 如果达到限制，事件日志中会记录一条警告，并且 IIS 日志中可能会记录 HTTP 500 响应。|此更改可以提升服务器总体性能。<br/><br/>若要还原旧行为，可以在 web.config 文件中添加下面的设置，从而选择禁用新行为。<br/><br/>`<appSettings>`<br/>&nbsp;&nbsp;&nbsp;`<add key="aspnet:RequestQueueLimitPerSession" value="2147483647"/>`<br/>`</appSettings>` | 边缘 |

## <a name="a-namewcf--windows-communication-foundation"></a><a name="WCF" />Windows Communication Foundation

| 功能  |更改  |影响 | 范围 | 
---------|---------|---------|-----|
| WCF 消息安全 | 在 .NET Framework 4.7 或更高版本控制下运行的应用程序可以通过应用程序配置设置在 WCF 消息安全设置中使用 TLS 1.1 和 TLS 1.2。 这是一项可以选择使用的功能；默认情况下，禁用对 WCF 消息安全设置中 TLS 1.1 和 TLS 1.2 的支持。 | WCF 消息安全的默认行为保持不变。 <br/><br/> 若要启用对 TLS 1.1 和 TLS 1.2 的支持，请在 `app.config` 或 `web.config` 文件的 [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中添加下面的配置设置：  <br/><br/>`<runtime>` <br/> &nbsp;&nbsp;&nbsp;`<AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;`<br/>&nbsp;&nbsp;&nbsp;`Switch.System.Net.DontEnableSchUseStrongCrypto=false" />`<br/>`</runtime>` | 边缘 |         

## <a name="a-namewpf--windows-presentation-foundation-wpf"></a><a name="WPF" />Windows Presentation Foundation (WPF)  

| 功能 | 更改 | 影响 | 范围 |
|---|---|---|---|
| <xref:System.Windows.Controls.Grid> 控件向 *-列分配空间 | 自定位 .NET Framework 4.7 的应用程序起，WPF 替换了 <xref:System.Windows.Controls.Grid> 控件用于向 \*-columns.md 分配空间的算法。 | 对于定位 .NET Framework 4.7 及更高版本的应用程序，此更改在许多情况下影响分配给 \*-列的实际宽度。 如果不需要此更改，可以在应用程序配置文件中添加条目，从而继续应用旧算法。 有关详细信息，请参阅[缓解：网格控件向 *-列分配空间](../../../docs/framework/migration-guide/mitigation-grid-control.md)。 | 次要 |
<xref:System.Windows.Media.ImageSourceConverter.ConvertFrom%2A> | 在面向 .NET Framework 4.6.2 及更低版本的应用程序中，<xref:System.Windows.Media.ImageSourceConverter.ConvertFrom%2A> 方法的异常处理代码中的错误会引发 <xref:System.NullReferenceException>，而不是预期的异常（如 <xref:System.IO.DirectoryNotFoundException> 或 <xref:System.IO.FileNotFoundException>）。<br/><br/>自定位 .NET Framework 4.7 的应用程序起，将抛出正确的异常。  | 对于面向 .NET Framework 4.7 且依赖处理 <xref:System.NullReferenceException> 的应用程序，可以在 `app.config` 文件的 [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中添加下面的配置设置，从而还原旧行为： <br/><br/>`<runtime>`<br/>&nbsp;&nbsp;&nbsp;`<AppContextSwitchOverrides value="Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true"/>`<br/>`</runtime>`| 边缘 | 
| 选择启用对基于 `WM_POINTER` 的触控/触笔堆栈的支持 | 自定位 .NET Framework 4.7 的应用程序起，WPF 现已开始支持可选的基于 WM_POINTER 的触控。  | 这是一项可以在 Windows 10 创意者更新及更高版本的 Windows 系统上选择使用的功能。 未显式选择启用基于指针的触控/触笔支持的 WPF 应用程序不会受到影响。 有关详细信息，请参阅[缓解：基于指针的触控和触笔支持](../Topic/Mitigation:%20Pointer-based%20Touch%20and%20Stylus%20Support.md)。 | 边缘 |
| <xref:System.Printing.PrintQueue> 类 | 自 .NET Framework 4.7 起，使用 <xref:System.Printing.PrintQueue> 的 WPF 打印 API 默认调用 Windows 打印文档包 API，而不调用现已弃用的 XPS 打印 API。<br/><br/>在旧版 Windows 上，旧打印堆栈继续像过去一样运行。 | 用户和开发者应该都不会看到任何行为或 API 使用变化。 <br/><br/>若要在 Windows 10 创意者更新中使用旧堆栈，请将 `HKEY_CURRENT_USER\Software\Microsoft.NETFramework\Windows Presentation Foundation\Printing` 注册表项的 `UseXpsOMPrinting` `REG_DWORD` 值设置为 1。 | 边缘 | 
## <a name="see-also"></a>请参阅
[.NET Framework 4.7 中的应用程序兼容性](Application%20Compatibility%20in%20the%20.NET%20Framework%204.7.md)

