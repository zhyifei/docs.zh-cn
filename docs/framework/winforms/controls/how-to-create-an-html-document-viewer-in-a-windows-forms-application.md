---
title: "如何：在 Windows 窗体应用程序中创建 HTML 文档查看器"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 00be8ca2e4e227b6e4593b0a9e32172ecb9457f5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a><span data-ttu-id="173f4-102">如何：在 Windows 窗体应用程序中创建 HTML 文档查看器</span><span class="sxs-lookup"><span data-stu-id="173f4-102">How to: Create an HTML Document Viewer in a Windows Forms Application</span></span>
<span data-ttu-id="173f4-103">你可以使用<xref:System.Windows.Forms.WebBrowser>控件来显示和打印 HTML 文档，而无需提供 Internet Web 浏览器的完整功能。</span><span class="sxs-lookup"><span data-stu-id="173f4-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to display and print HTML documents without providing the full functionality of an Internet Web browser.</span></span> <span data-ttu-id="173f4-104">当你想要充分利用 HTML 格式设置功能，但不是希望用户可以加载可能包含不受信任的 Web 控件或潜在的恶意脚本代码的任意网页，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="173f4-104">This is useful when you want to take advantage of the formatting capabilities of HTML but do not want your users to load arbitrary Web pages that may contain untrusted Web controls or potentially malicious script code.</span></span> <span data-ttu-id="173f4-105">你可能想要限制的功能<xref:System.Windows.Forms.WebBrowser>控制这种方式，例如，若要将其用作 HTML 电子邮件查看器，或以 HTML 格式在中提供帮助你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="173f4-105">You might want to restrict the capability of the <xref:System.Windows.Forms.WebBrowser> control in this manner, for example, to use it as an HTML e-mail viewer or to provide HTML-formatted help in your application.</span></span>  
  
### <a name="to-create-an-html-document-viewer"></a><span data-ttu-id="173f4-106">若要创建 HTML 文档查看器</span><span class="sxs-lookup"><span data-stu-id="173f4-106">To create an HTML document viewer</span></span>  
  
1.  <span data-ttu-id="173f4-107">设置<xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>属性`false`以防止<xref:System.Windows.Forms.WebBrowser>控件打开放到其上的文件。</span><span class="sxs-lookup"><span data-stu-id="173f4-107">Set the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>  
  
     [!code-csharp[WebBrowserMisc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2.  <span data-ttu-id="173f4-108">设置<xref:System.Windows.Forms.WebBrowser.Url%2A>属性显示的初始文件的位置。</span><span class="sxs-lookup"><span data-stu-id="173f4-108">Set the <xref:System.Windows.Forms.WebBrowser.Url%2A> property to the location of the initial file to display.</span></span>  
  
     [!code-csharp[WebBrowserMisc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="173f4-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="173f4-109">Compiling the Code</span></span>  
 <span data-ttu-id="173f4-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="173f4-110">This example requires:</span></span>  
  
-   <span data-ttu-id="173f4-111">名为 `webBrowser1` 的 <xref:System.Windows.Forms.WebBrowser> 控件。</span><span class="sxs-lookup"><span data-stu-id="173f4-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
-   <span data-ttu-id="173f4-112">对 `System` 和 `System.Windows.Forms` 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="173f4-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="173f4-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="173f4-113">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>  
 <xref:System.Windows.Forms.WebBrowser.Url%2A>  
 [<span data-ttu-id="173f4-114">WebBrowser 控件概述</span><span class="sxs-lookup"><span data-stu-id="173f4-114">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [<span data-ttu-id="173f4-115">WebBrowser 安全</span><span class="sxs-lookup"><span data-stu-id="173f4-115">WebBrowser Security</span></span>](../../../../docs/framework/winforms/controls/webbrowser-security.md)  
 [<span data-ttu-id="173f4-116">如何：使用 WebBrowser 控件转到 URL</span><span class="sxs-lookup"><span data-stu-id="173f4-116">How to: Navigate to a URL with the WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)  
 [<span data-ttu-id="173f4-117">如何：使用 WebBrowser 控件进行打印</span><span class="sxs-lookup"><span data-stu-id="173f4-117">How to: Print with a WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)
