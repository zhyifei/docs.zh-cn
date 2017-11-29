---
title: "如何：在托管 HTML 文档对象模型中访问 HTML 源"
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
- managed HTML DOM
- HTML [Windows Forms], accessing in Windows Forms
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7ef9839029e1c60cbc0d713e8982baa5708a281f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-the-html-source-in-the-managed-html-document-object-model"></a><span data-ttu-id="1e995-102">如何：在托管 HTML 文档对象模型中访问 HTML 源</span><span class="sxs-lookup"><span data-stu-id="1e995-102">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>
<span data-ttu-id="1e995-103"><xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> 控件中的 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 和 <xref:System.Windows.Forms.WebBrowser> 属性返回当前文档的 HTML，显示方式与第一次显示的一样。</span><span class="sxs-lookup"><span data-stu-id="1e995-103">The <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> and <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> properties on the <xref:System.Windows.Forms.WebBrowser> control return the HTML of the current document as it existed when it was first displayed.</span></span> <span data-ttu-id="1e995-104">但是，如果通过使用方法和属性调用（例如 <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> 和 <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>）修改此页面，则在调用 <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> 和 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 时不会显示这些更改。</span><span class="sxs-lookup"><span data-stu-id="1e995-104">However, if you modify the page using method and property calls such as <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> and <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>, these changes will not appear when you call <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> and <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>.</span></span> <span data-ttu-id="1e995-105">若要获得 DOM 的最新 HTML 源，必须调用 HTML 元素上的 <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="1e995-105">To obtain the most up-to-date HTML source for the DOM, you must call the <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> property on the HTML element.</span></span>  
  
 <span data-ttu-id="1e995-106">以下过程显示了如何检索动态源并将其显示在单独的快捷菜单中。</span><span class="sxs-lookup"><span data-stu-id="1e995-106">The following procedure shows how to retrieve the dynamic source and display it in a separate shortcut menu.</span></span>  
  
### <a name="retrieving-the-dynamic-source-with-the-outerhtml-property"></a><span data-ttu-id="1e995-107">使用 OuterHtml 属性检索动态源</span><span class="sxs-lookup"><span data-stu-id="1e995-107">Retrieving the dynamic source with the OuterHtml property</span></span>  
  
1.  <span data-ttu-id="1e995-108">创建新的 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e995-108">Create a new Windows Forms application.</span></span> <span data-ttu-id="1e995-109">首先创建一个<xref:System.Windows.Forms.Form>，并调用它`Form1`。</span><span class="sxs-lookup"><span data-stu-id="1e995-109">Start with a single <xref:System.Windows.Forms.Form>, and call it `Form1`.</span></span>  
  
2.  <span data-ttu-id="1e995-110">主机<xref:System.Windows.Forms.WebBrowser>控制在 Windows 窗体应用程序，并将其命名`WebBrowser1`。</span><span class="sxs-lookup"><span data-stu-id="1e995-110">Host the <xref:System.Windows.Forms.WebBrowser> control in your Windows Forms application, and name it `WebBrowser1`.</span></span> <span data-ttu-id="1e995-111">有关详细信息，请参阅[如何： 将 Web 浏览器功能添加 Windows 窗体应用程序](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)。</span><span class="sxs-lookup"><span data-stu-id="1e995-111">For more information, see [How to: Add Web Browser Capabilities to a Windows Forms Application](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).</span></span>  
  
3.  <span data-ttu-id="1e995-112">创建第二个<xref:System.Windows.Forms.Form>调用应用程序中`CodeForm`。</span><span class="sxs-lookup"><span data-stu-id="1e995-112">Create a second <xref:System.Windows.Forms.Form> in your application called `CodeForm`.</span></span>  
  
4.  <span data-ttu-id="1e995-113">添加<xref:System.Windows.Forms.RichTextBox>控制转移到`CodeForm`并设置其<xref:System.Windows.Forms.Control.Dock%2A>属性`Fill`。</span><span class="sxs-lookup"><span data-stu-id="1e995-113">Add a <xref:System.Windows.Forms.RichTextBox> control to `CodeForm` and set its <xref:System.Windows.Forms.Control.Dock%2A> property to `Fill`.</span></span>  
  
5.  <span data-ttu-id="1e995-114">创建一个公共属性上`CodeForm`调用`Code`。</span><span class="sxs-lookup"><span data-stu-id="1e995-114">Create a public property on `CodeForm` called `Code`.</span></span>  
  
     [!code-csharp[DisplayWebBrowserCode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6.  <span data-ttu-id="1e995-115">添加<xref:System.Windows.Forms.Button>控件名为`Button1`到你<xref:System.Windows.Forms.Form>，并监视的<xref:System.Windows.Forms.Control.Click>事件。</span><span class="sxs-lookup"><span data-stu-id="1e995-115">Add a <xref:System.Windows.Forms.Button> control named `Button1` to your <xref:System.Windows.Forms.Form>, and monitor for the <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="1e995-116">有关监视事件的详细信息，请参阅[事件](../../../../docs/standard/events/index.md)。</span><span class="sxs-lookup"><span data-stu-id="1e995-116">For details on monitoring events, see [Events](../../../../docs/standard/events/index.md).</span></span>  
  
7.  <span data-ttu-id="1e995-117">将以下代码添加到 <xref:System.Windows.Forms.Control.Click> 事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="1e995-117">Add the following code to the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
     [!code-csharp[DisplayWebBrowserCode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## <a name="robust-programming"></a><span data-ttu-id="1e995-118">可靠编程</span><span class="sxs-lookup"><span data-stu-id="1e995-118">Robust Programming</span></span>  
 <span data-ttu-id="1e995-119">在尝试检索 <xref:System.Windows.Forms.WebBrowser.Document%2A> 之前，应总是先测试它的值。</span><span class="sxs-lookup"><span data-stu-id="1e995-119">Always test the value of <xref:System.Windows.Forms.WebBrowser.Document%2A> before attempting to retrieve it.</span></span> <span data-ttu-id="1e995-120">如果当前页未完成加载，则 <xref:System.Windows.Forms.WebBrowser.Document%2A> 或它的一个或多个子对象可能无法初始化。</span><span class="sxs-lookup"><span data-stu-id="1e995-120">If the current page is not finished loading, <xref:System.Windows.Forms.WebBrowser.Document%2A> or one or more of its child objects may not be initialized.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e995-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e995-121">See Also</span></span>  
 [<span data-ttu-id="1e995-122">使用托管 HTML 文档对象模型</span><span class="sxs-lookup"><span data-stu-id="1e995-122">Using the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)  
 [<span data-ttu-id="1e995-123">WebBrowser 控件概述</span><span class="sxs-lookup"><span data-stu-id="1e995-123">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)
