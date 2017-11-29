---
title: "WebBrowser 控件（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WebBrowser control [Windows Forms]
- Web pages [Windows Forms], hosting in applications
- Web pages [Windows Forms], Windows Forms controls
ms.assetid: 12667861-5b5b-46bc-8fb5-675e25264c9f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0a87c1cd87b21b10404ae4a19ee931cc5f69ece
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="webbrowser-control-windows-forms"></a><span data-ttu-id="996c5-102">WebBrowser 控件（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="996c5-102">WebBrowser Control (Windows Forms)</span></span>
<span data-ttu-id="996c5-103">Windows 窗体`WebBrowser`的控件承载网页并提供 Web 浏览到你的应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="996c5-103">The Windows Forms `WebBrowser` control hosts Web pages and provides Web browsing capabilities to your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="996c5-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="996c5-104">In This Section</span></span>  
 [<span data-ttu-id="996c5-105">WebBrowser 控件概述</span><span class="sxs-lookup"><span data-stu-id="996c5-105">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 <span data-ttu-id="996c5-106">说明此控件的本质及其主要功能和属性。</span><span class="sxs-lookup"><span data-stu-id="996c5-106">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="996c5-107">WebBrowser 安全</span><span class="sxs-lookup"><span data-stu-id="996c5-107">WebBrowser Security</span></span>](../../../../docs/framework/winforms/controls/webbrowser-security.md)  
 <span data-ttu-id="996c5-108">说明与控件相关的安全问题。</span><span class="sxs-lookup"><span data-stu-id="996c5-108">Explains security issues related to the control.</span></span>  
  
 [<span data-ttu-id="996c5-109">如何：使用 WebBrowser 控件转到 URL</span><span class="sxs-lookup"><span data-stu-id="996c5-109">How to: Navigate to a URL with the WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)  
 <span data-ttu-id="996c5-110">演示如何使用控件导航到特定的 URL。</span><span class="sxs-lookup"><span data-stu-id="996c5-110">Demonstrates how to use the control to navigate to a specific URL.</span></span>  
  
 [<span data-ttu-id="996c5-111">如何：使用 WebBrowser 控件进行打印</span><span class="sxs-lookup"><span data-stu-id="996c5-111">How to: Print with a WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)  
 <span data-ttu-id="996c5-112">演示如何打印网页而不显示它。</span><span class="sxs-lookup"><span data-stu-id="996c5-112">Demonstrates how to print a Web page without displaying it.</span></span>  
  
 [<span data-ttu-id="996c5-113">如何：向 Windows 窗体应用程序添加 Web 浏览器功能</span><span class="sxs-lookup"><span data-stu-id="996c5-113">How to: Add Web Browser Capabilities to a Windows Forms Application</span></span>](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)  
 <span data-ttu-id="996c5-114">描述如何将初始化为的 Web 浏览器使用的控件。</span><span class="sxs-lookup"><span data-stu-id="996c5-114">Describes how to initialize the control for use as a Web browser.</span></span>  
  
 [<span data-ttu-id="996c5-115">如何：在 Windows 窗体应用程序中创建 HTML 文档查看器</span><span class="sxs-lookup"><span data-stu-id="996c5-115">How to: Create an HTML Document Viewer in a Windows Forms Application</span></span>](../../../../docs/framework/winforms/controls/how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)  
 <span data-ttu-id="996c5-116">描述如何将初始化为 HTML 查看器使用的控件。</span><span class="sxs-lookup"><span data-stu-id="996c5-116">Describes how to initialize the control for use as an HTML viewer.</span></span>  
  
 [<span data-ttu-id="996c5-117">如何：在 DHTML 代码和客户端应用程序代码之间实现双向通信</span><span class="sxs-lookup"><span data-stu-id="996c5-117">How to: Implement Two-Way Communication Between DHTML Code and Client Application Code</span></span>](../../../../docs/framework/winforms/controls/implement-two-way-com-between-dhtml-and-client.md)  
 <span data-ttu-id="996c5-118">描述如何设置你的应用程序代码与 DHTML 之间由控件托管的 Web 页面中的双向通信。</span><span class="sxs-lookup"><span data-stu-id="996c5-118">Describes how to set up two-way communication between your application code and DHTML in a Web page hosted by the control.</span></span>  
  
 [<span data-ttu-id="996c5-119">使用托管 HTML 文档对象模型</span><span class="sxs-lookup"><span data-stu-id="996c5-119">Using the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)  
 <span data-ttu-id="996c5-120">提供一些主题，介绍如何操作或创建 HTML 页面，由托管<xref:System.Windows.Forms.WebBrowser>控件。</span><span class="sxs-lookup"><span data-stu-id="996c5-120">Provides topics that describe how to manipulate or create HTML pages hosted by the <xref:System.Windows.Forms.WebBrowser> control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="996c5-121">参考</span><span class="sxs-lookup"><span data-stu-id="996c5-121">Reference</span></span>  
 <span data-ttu-id="996c5-122"><xref:System.Windows.Forms.WebBrowser> 类</span><span class="sxs-lookup"><span data-stu-id="996c5-122"><xref:System.Windows.Forms.WebBrowser> class</span></span>  
 <span data-ttu-id="996c5-123">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="996c5-123">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventArgs>  
 <span data-ttu-id="996c5-124">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="996c5-124">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventHandler>  
 <span data-ttu-id="996c5-125">描述该委托。</span><span class="sxs-lookup"><span data-stu-id="996c5-125">Describes this delegate.</span></span>  
  
 <xref:System.Windows.Forms.WebBrowserEncryptionLevel>  
 <span data-ttu-id="996c5-126">介绍此枚举，其所有值。</span><span class="sxs-lookup"><span data-stu-id="996c5-126">Describes this enumeration and all its values.</span></span>  
  
 <xref:System.Windows.Forms.WebBrowserNavigatedEventArgs>  
 <span data-ttu-id="996c5-127">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="996c5-127">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.WebBrowserNavigatedEventHandler>  
 <span data-ttu-id="996c5-128">描述该委托。</span><span class="sxs-lookup"><span data-stu-id="996c5-128">Describes this delegate.</span></span>  
  
 <xref:System.Windows.Forms.WebBrowserNavigatingEventArgs>  
 <span data-ttu-id="996c5-129">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="996c5-129">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.WebBrowserNavigatingEventHandler>  
 <span data-ttu-id="996c5-130">描述该委托。</span><span class="sxs-lookup"><span data-stu-id="996c5-130">Describes this delegate.</span></span>  
  
 <xref:System.Windows.Forms.WebBrowserProgressChangedEventArgs>  
 <span data-ttu-id="996c5-131">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="996c5-131">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.WebBrowserProgressChangedEventHandler>  
 <span data-ttu-id="996c5-132">描述该委托。</span><span class="sxs-lookup"><span data-stu-id="996c5-132">Describes this delegate.</span></span>  
  
 <xref:System.Windows.Forms.WebBrowserReadyState>  
 <span data-ttu-id="996c5-133">介绍此枚举，其所有值。</span><span class="sxs-lookup"><span data-stu-id="996c5-133">Describes this enumeration and all its values.</span></span>  
  
 <xref:System.Windows.Forms.WebBrowserRefreshOption>  
 <span data-ttu-id="996c5-134">介绍此枚举，其所有值。</span><span class="sxs-lookup"><span data-stu-id="996c5-134">Describes this enumeration and all its values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="996c5-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="996c5-135">See Also</span></span>  
 [<span data-ttu-id="996c5-136">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="996c5-136">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
