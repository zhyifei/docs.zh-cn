---
title: "WebBrowser 控件概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: WebBrowser
helpviewer_keywords:
- WebBrowser control [Windows Forms], about
- Web pages [Windows Forms], displaying in applications
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d2c1ed93769cc91d9622a86ea2d894cea57f5bcd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="webbrowser-control-overview"></a>WebBrowser 控件概述
<xref:System.Windows.Forms.WebBrowser>控件 WebBrowser ActiveX 控件提供托管的包装。 托管的包装便可以在 Windows 窗体客户端应用程序中显示网页。 你可以使用<xref:System.Windows.Forms.WebBrowser>控件重复中你的应用程序或你的 Internet Explorer Web 浏览功能可以禁用默认 Internet 资源管理器功能和控件用作简单的 HTML 文档查看器。 你可以使用控件以将基于 DHTML 的用户界面元素添加到你的窗体和隐藏它们是否承载在事实<xref:System.Windows.Forms.WebBrowser>控件。 这种方法，可以无缝组合与单个应用程序中的 Windows 窗体控件的 Web 控件。  
  
## <a name="frequently-used-properties-methods-and-events"></a>经常使用的属性、 方法和事件  
 <xref:System.Windows.Forms.WebBrowser>控件具有多个属性、 方法和事件，可以将用于实现在 Internet Explorer 中找到的控件。 例如，你可以使用`Navigate`方法以实现地址栏中，与`GoBack`， `GoForward`， `Stop`，和`Refresh`方法来实现工具栏上的导航按钮。 你可以处理`Navigated`事件以更新地址栏中的值与`Url`属性和值为标题栏`DocumentTitle`属性。  
  
 如果你想要生成你自己应用程序中的页面内容，则可以设置`DocumentText`属性。 如果你熟悉 HTML 文档对象模型 (DOM)，您还可以操作通过在当前网页的内容`Document`属性。 通过此属性，您可以存储和修改而不是在文件之间导航的内存中的文档。  
  
 `Document`属性，您还可以调用 Web 页的脚本在客户端应用程序代码中的代码中实现的方法。 若要在脚本代码中访问客户端应用程序代码中，设置`ObjectForScripting`属性。 你指定的对象可以访问你的脚本代码作为`window.external`对象。  
  
|name|描述|  
|----------|-----------------|  
|<xref:System.Windows.Forms.WebBrowser.Document%2A> 属性|获取一个对象，提供对 HTML 文档对象模型 (DOM) 的当前网页的托管的访问。|  
|<xref:System.Windows.Forms.WebBrowser.DocumentCompleted>事件|当 Web 页面完成加载时出现。|  
|<xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 属性|获取或设置 HTML 当前网页的内容。|  
|<xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A> 属性|获取当前网页的标题。|  
|<xref:System.Windows.Forms.WebBrowser.GoBack%2A> 方法|导航至历史记录中的上一页。|  
|<xref:System.Windows.Forms.WebBrowser.GoForward%2A> 方法|导航至历史记录中的下一页。|  
|<xref:System.Windows.Forms.WebBrowser.Navigate%2A> 方法|导航到指定的 URL。|  
|<xref:System.Windows.Forms.WebBrowser.Navigating>事件|导航开始，启用要取消的操作之前发生。|  
|<xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> 属性|获取或设置 Web 页上的脚本代码可以使用与你的应用程序进行通信的对象。|  
|<xref:System.Windows.Forms.WebBrowser.Print%2A> 方法|打印当前的 Web 页。|  
|<xref:System.Windows.Forms.WebBrowser.Refresh%2A> 方法|将重新加载当前的 Web 页。|  
|<xref:System.Windows.Forms.WebBrowser.Stop%2A> 方法|将暂停当前导航并停止动态页元素，如声音和动画。|  
|<xref:System.Windows.Forms.WebBrowser.Url%2A> 属性|获取或设置当前网页的 URL。 设置此属性导航到新 URL 的控件。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventArgs>  
 <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventHandler>  
 <xref:System.Windows.Forms.WebBrowserEncryptionLevel>  
 <xref:System.Windows.Forms.WebBrowserNavigatedEventArgs>  
 <xref:System.Windows.Forms.WebBrowserNavigatedEventHandler>  
 <xref:System.Windows.Forms.WebBrowserNavigatingEventArgs>  
 <xref:System.Windows.Forms.WebBrowserNavigatingEventHandler>  
 <xref:System.Windows.Forms.WebBrowserProgressChangedEventArgs>  
 <xref:System.Windows.Forms.WebBrowserReadyState>  
 <xref:System.Windows.Forms.WebBrowserRefreshOption>  
 [如何：使用 WebBrowser 控件转到 URL](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)  
 [如何：使用 WebBrowser 控件进行打印](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)  
 [如何：向 Windows 窗体应用程序添加 Web 浏览器功能](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)  
 [如何：在 Windows 窗体应用程序中创建 HTML 文档查看器](../../../../docs/framework/winforms/controls/how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)  
 [如何：在 DHTML 代码和客户端应用程序代码之间实现双向通信](../../../../docs/framework/winforms/controls/implement-two-way-com-between-dhtml-and-client.md)  
 [WebBrowser 安全](../../../../docs/framework/winforms/controls/webbrowser-security.md)
