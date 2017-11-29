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
ms.openlocfilehash: 9c2dfae4cbd7f583ce69ff5591c24a573db0d4e4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="webbrowser-control-overview"></a><span data-ttu-id="05b94-102">WebBrowser 控件概述</span><span class="sxs-lookup"><span data-stu-id="05b94-102">WebBrowser Control Overview</span></span>
<span data-ttu-id="05b94-103"><xref:System.Windows.Forms.WebBrowser>控件 WebBrowser ActiveX 控件提供托管的包装。</span><span class="sxs-lookup"><span data-stu-id="05b94-103">The <xref:System.Windows.Forms.WebBrowser> control provides a managed wrapper for the WebBrowser ActiveX control.</span></span> <span data-ttu-id="05b94-104">托管的包装便可以在 Windows 窗体客户端应用程序中显示网页。</span><span class="sxs-lookup"><span data-stu-id="05b94-104">The managed wrapper lets you display Web pages in your Windows Forms client applications.</span></span> <span data-ttu-id="05b94-105">你可以使用<xref:System.Windows.Forms.WebBrowser>控件重复中你的应用程序或你的 Internet Explorer Web 浏览功能可以禁用默认 Internet 资源管理器功能和控件用作简单的 HTML 文档查看器。</span><span class="sxs-lookup"><span data-stu-id="05b94-105">You can use the <xref:System.Windows.Forms.WebBrowser> control to duplicate Internet Explorer Web browsing functionality in your application or you can disable default Internet Explorer functionality and use the control as a simple HTML document viewer.</span></span> <span data-ttu-id="05b94-106">你可以使用控件以将基于 DHTML 的用户界面元素添加到你的窗体和隐藏它们是否承载在事实<xref:System.Windows.Forms.WebBrowser>控件。</span><span class="sxs-lookup"><span data-stu-id="05b94-106">You can also use the control to add DHTML-based user interface elements to your form and hide the fact that they are hosted in the <xref:System.Windows.Forms.WebBrowser> control.</span></span> <span data-ttu-id="05b94-107">这种方法，可以无缝组合与单个应用程序中的 Windows 窗体控件的 Web 控件。</span><span class="sxs-lookup"><span data-stu-id="05b94-107">This approach lets you seamlessly combine Web controls with Windows Forms controls in a single application.</span></span>  
  
## <a name="frequently-used-properties-methods-and-events"></a><span data-ttu-id="05b94-108">经常使用的属性、 方法和事件</span><span class="sxs-lookup"><span data-stu-id="05b94-108">Frequently Used Properties, Methods, and Events</span></span>  
 <span data-ttu-id="05b94-109"><xref:System.Windows.Forms.WebBrowser>控件具有多个属性、 方法和事件，可以将用于实现在 Internet Explorer 中找到的控件。</span><span class="sxs-lookup"><span data-stu-id="05b94-109">The <xref:System.Windows.Forms.WebBrowser> control has several properties, methods, and events that you can use to implement controls found in Internet Explorer.</span></span> <span data-ttu-id="05b94-110">例如，你可以使用`Navigate`方法以实现地址栏中，与`GoBack`， `GoForward`， `Stop`，和`Refresh`方法来实现工具栏上的导航按钮。</span><span class="sxs-lookup"><span data-stu-id="05b94-110">For example, you can use the `Navigate` method to implement an address bar, and the `GoBack`, `GoForward`, `Stop`, and `Refresh` methods to implement navigation buttons on a toolbar.</span></span> <span data-ttu-id="05b94-111">你可以处理`Navigated`事件以更新地址栏中的值与`Url`属性和值为标题栏`DocumentTitle`属性。</span><span class="sxs-lookup"><span data-stu-id="05b94-111">You can handle the `Navigated` event to update the address bar with the value of the `Url` property and the title bar with the value of the `DocumentTitle` property.</span></span>  
  
 <span data-ttu-id="05b94-112">如果你想要生成你自己应用程序中的页面内容，则可以设置`DocumentText`属性。</span><span class="sxs-lookup"><span data-stu-id="05b94-112">If you want to generate your own page content within your application, you can set the `DocumentText` property.</span></span> <span data-ttu-id="05b94-113">如果你熟悉 HTML 文档对象模型 (DOM)，您还可以操作通过在当前网页的内容`Document`属性。</span><span class="sxs-lookup"><span data-stu-id="05b94-113">If you are familiar with the HTML document object model (DOM), you can also manipulate the contents of the current Web page through the `Document` property.</span></span> <span data-ttu-id="05b94-114">通过此属性，您可以存储和修改而不是在文件之间导航的内存中的文档。</span><span class="sxs-lookup"><span data-stu-id="05b94-114">With this property, you can store and modify documents in memory instead of navigating among files.</span></span>  
  
 <span data-ttu-id="05b94-115">`Document`属性，您还可以调用 Web 页的脚本在客户端应用程序代码中的代码中实现的方法。</span><span class="sxs-lookup"><span data-stu-id="05b94-115">The `Document` property also lets you call methods implemented in Web page scripting code from your client application code.</span></span> <span data-ttu-id="05b94-116">若要在脚本代码中访问客户端应用程序代码中，设置`ObjectForScripting`属性。</span><span class="sxs-lookup"><span data-stu-id="05b94-116">To access your client application code from your scripting code, set the `ObjectForScripting` property.</span></span> <span data-ttu-id="05b94-117">你指定的对象可以访问你的脚本代码作为`window.external`对象。</span><span class="sxs-lookup"><span data-stu-id="05b94-117">The object that you specify can be accessed by your script code as the `window.external` object.</span></span>  
  
|<span data-ttu-id="05b94-118">名称</span><span class="sxs-lookup"><span data-stu-id="05b94-118">Name</span></span>|<span data-ttu-id="05b94-119">描述</span><span class="sxs-lookup"><span data-stu-id="05b94-119">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="05b94-120"><xref:System.Windows.Forms.WebBrowser.Document%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="05b94-120"><xref:System.Windows.Forms.WebBrowser.Document%2A> property</span></span>|<span data-ttu-id="05b94-121">获取一个对象，提供对 HTML 文档对象模型 (DOM) 的当前网页的托管的访问。</span><span class="sxs-lookup"><span data-stu-id="05b94-121">Gets an object that provides managed access to the HTML document object model (DOM) of the current Web page.</span></span>|  
|<span data-ttu-id="05b94-122"><xref:System.Windows.Forms.WebBrowser.DocumentCompleted>事件</span><span class="sxs-lookup"><span data-stu-id="05b94-122"><xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event</span></span>|<span data-ttu-id="05b94-123">当 Web 页面完成加载时出现。</span><span class="sxs-lookup"><span data-stu-id="05b94-123">Occurs when a Web page finishes loading.</span></span>|  
|<span data-ttu-id="05b94-124"><xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="05b94-124"><xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property</span></span>|<span data-ttu-id="05b94-125">获取或设置 HTML 当前网页的内容。</span><span class="sxs-lookup"><span data-stu-id="05b94-125">Gets or sets the HTML content of the current Web page.</span></span>|  
|<span data-ttu-id="05b94-126"><xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="05b94-126"><xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A> property</span></span>|<span data-ttu-id="05b94-127">获取当前网页的标题。</span><span class="sxs-lookup"><span data-stu-id="05b94-127">Gets the title of the current Web page.</span></span>|  
|<span data-ttu-id="05b94-128"><xref:System.Windows.Forms.WebBrowser.GoBack%2A> 方法</span><span class="sxs-lookup"><span data-stu-id="05b94-128"><xref:System.Windows.Forms.WebBrowser.GoBack%2A> method</span></span>|<span data-ttu-id="05b94-129">导航至历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="05b94-129">Navigates to the previous page in history.</span></span>|  
|<span data-ttu-id="05b94-130"><xref:System.Windows.Forms.WebBrowser.GoForward%2A> 方法</span><span class="sxs-lookup"><span data-stu-id="05b94-130"><xref:System.Windows.Forms.WebBrowser.GoForward%2A> method</span></span>|<span data-ttu-id="05b94-131">导航至历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="05b94-131">Navigates to the next page in history.</span></span>|  
|<span data-ttu-id="05b94-132"><xref:System.Windows.Forms.WebBrowser.Navigate%2A> 方法</span><span class="sxs-lookup"><span data-stu-id="05b94-132"><xref:System.Windows.Forms.WebBrowser.Navigate%2A> method</span></span>|<span data-ttu-id="05b94-133">导航到指定的 URL。</span><span class="sxs-lookup"><span data-stu-id="05b94-133">Navigates to the specified URL.</span></span>|  
|<span data-ttu-id="05b94-134"><xref:System.Windows.Forms.WebBrowser.Navigating>事件</span><span class="sxs-lookup"><span data-stu-id="05b94-134"><xref:System.Windows.Forms.WebBrowser.Navigating> event</span></span>|<span data-ttu-id="05b94-135">导航开始，启用要取消的操作之前发生。</span><span class="sxs-lookup"><span data-stu-id="05b94-135">Occurs before navigation begins, enabling the action to be canceled.</span></span>|  
|<span data-ttu-id="05b94-136"><xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="05b94-136"><xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> property</span></span>|<span data-ttu-id="05b94-137">获取或设置 Web 页上的脚本代码可以使用与你的应用程序进行通信的对象。</span><span class="sxs-lookup"><span data-stu-id="05b94-137">Gets or sets an object that Web page scripting code can use to communicate with your application.</span></span>|  
|<span data-ttu-id="05b94-138"><xref:System.Windows.Forms.WebBrowser.Print%2A> 方法</span><span class="sxs-lookup"><span data-stu-id="05b94-138"><xref:System.Windows.Forms.WebBrowser.Print%2A> method</span></span>|<span data-ttu-id="05b94-139">打印当前的 Web 页。</span><span class="sxs-lookup"><span data-stu-id="05b94-139">Prints the current Web page.</span></span>|  
|<span data-ttu-id="05b94-140"><xref:System.Windows.Forms.WebBrowser.Refresh%2A> 方法</span><span class="sxs-lookup"><span data-stu-id="05b94-140"><xref:System.Windows.Forms.WebBrowser.Refresh%2A> method</span></span>|<span data-ttu-id="05b94-141">将重新加载当前的 Web 页。</span><span class="sxs-lookup"><span data-stu-id="05b94-141">Reloads the current Web page.</span></span>|  
|<span data-ttu-id="05b94-142"><xref:System.Windows.Forms.WebBrowser.Stop%2A> 方法</span><span class="sxs-lookup"><span data-stu-id="05b94-142"><xref:System.Windows.Forms.WebBrowser.Stop%2A> method</span></span>|<span data-ttu-id="05b94-143">将暂停当前导航并停止动态页元素，如声音和动画。</span><span class="sxs-lookup"><span data-stu-id="05b94-143">Halts the current navigation and stops dynamic page elements such as sounds and animation.</span></span>|  
|<span data-ttu-id="05b94-144"><xref:System.Windows.Forms.WebBrowser.Url%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="05b94-144"><xref:System.Windows.Forms.WebBrowser.Url%2A> property</span></span>|<span data-ttu-id="05b94-145">获取或设置当前网页的 URL。</span><span class="sxs-lookup"><span data-stu-id="05b94-145">Gets or sets the URL of the current Web page.</span></span> <span data-ttu-id="05b94-146">设置此属性导航到新 URL 的控件。</span><span class="sxs-lookup"><span data-stu-id="05b94-146">Setting this property navigates the control to the new URL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05b94-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05b94-147">See Also</span></span>  
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
 [<span data-ttu-id="05b94-148">如何：使用 WebBrowser 控件转到 URL</span><span class="sxs-lookup"><span data-stu-id="05b94-148">How to: Navigate to a URL with the WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)  
 [<span data-ttu-id="05b94-149">如何：使用 WebBrowser 控件进行打印</span><span class="sxs-lookup"><span data-stu-id="05b94-149">How to: Print with a WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)  
 [<span data-ttu-id="05b94-150">如何：向 Windows 窗体应用程序添加 Web 浏览器功能</span><span class="sxs-lookup"><span data-stu-id="05b94-150">How to: Add Web Browser Capabilities to a Windows Forms Application</span></span>](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)  
 [<span data-ttu-id="05b94-151">如何：在 Windows 窗体应用程序中创建 HTML 文档查看器</span><span class="sxs-lookup"><span data-stu-id="05b94-151">How to: Create an HTML Document Viewer in a Windows Forms Application</span></span>](../../../../docs/framework/winforms/controls/how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)  
 [<span data-ttu-id="05b94-152">如何：在 DHTML 代码和客户端应用程序代码之间实现双向通信</span><span class="sxs-lookup"><span data-stu-id="05b94-152">How to: Implement Two-Way Communication Between DHTML Code and Client Application Code</span></span>](../../../../docs/framework/winforms/controls/implement-two-way-com-between-dhtml-and-client.md)  
 [<span data-ttu-id="05b94-153">WebBrowser 安全</span><span class="sxs-lookup"><span data-stu-id="05b94-153">WebBrowser Security</span></span>](../../../../docs/framework/winforms/controls/webbrowser-security.md)
