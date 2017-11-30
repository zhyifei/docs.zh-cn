---
title: "使用 .NET Framework 开发客户端应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- client application services
- applications [Windows Forms]
- Windows Presentation Foundation, in Visual Studio
- WPF, in Visual Studio
- Windows applications
- rich client applications
- .NET applications, Windows applications
- Visual Basic code, creating applications
- Visual C#, creating applications
- client/server applications, Windows applications
ms.assetid: 2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: daf09f94b4c0854365274773f8c426cc07e8c6dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="developing-client-applications-with-the-net-framework"></a><span data-ttu-id="7a730-102">使用 .NET Framework 开发客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="7a730-102">Developing Client Applications with the .NET Framework</span></span>
<span data-ttu-id="7a730-103">利用在用户的计算机或设备本地运行的 .NET Framework，有多种方法开发基于 Windows 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a730-103">There are multiple ways to develop Windows-based applications with the .NET framework that run locally on users' computers or devices.</span></span> <span data-ttu-id="7a730-104">本节包含的主题价始了如何使用 Windows Presentation Foundation (WPF) 或 Windows 窗体创建基于 Windows 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a730-104">This section contains topics that describe how to create Windows-based applications by using Windows Presentation Foundation (WPF) or by using Windows Forms.</span></span> <span data-ttu-id="7a730-105">不过，也可以利用 .NET Framework 创建 Web 应用程序，以及通过 Windows 应用商店或 Windows Phone 应用商店发布的面向计算机或设备的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a730-105">However, you can also create web applications using the .NET Framework, and client applications for computers or devices that you make available through the Windows Store or Windows Phone Store.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7a730-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="7a730-106">In This Section</span></span>  
 [<span data-ttu-id="7a730-107">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="7a730-107">Windows Presentation Foundation</span></span>](../../docs/framework/wpf/index.md)  
 <span data-ttu-id="7a730-108">提供有关使用 WPF 开发和部署应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="7a730-108">Provides information about developing applications by using WPF.</span></span>  
  
 [<span data-ttu-id="7a730-109">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="7a730-109">Windows Forms</span></span>](../../docs/framework/winforms/index.md)  
 <span data-ttu-id="7a730-110">提供有关使用 Windows 窗体开发和部署应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="7a730-110">Provides information about developing applications by using Windows Forms.</span></span>  
  
 [<span data-ttu-id="7a730-111">常用的客户端技术</span><span class="sxs-lookup"><span data-stu-id="7a730-111">Common Client Technologies</span></span>](../../docs/framework/common-client-technologies/index.md)  
 <span data-ttu-id="7a730-112">提供有关在开发客户端应用程序时可使用的其他技术的信息。</span><span class="sxs-lookup"><span data-stu-id="7a730-112">Provides information about additional technologies that can be used when developing client applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7a730-113">相关章节</span><span class="sxs-lookup"><span data-stu-id="7a730-113">Related Sections</span></span>  
 [<span data-ttu-id="7a730-114">Windows 应用商店应用</span><span class="sxs-lookup"><span data-stu-id="7a730-114">Windows Store apps</span></span>](http://msdn.microsoft.com/windows/apps/)  
 <span data-ttu-id="7a730-115">介绍如何创建可以通过 Windows 应用商店向用户提供的应用</span><span class="sxs-lookup"><span data-stu-id="7a730-115">Describes how to create apps that you can make available to users through the Windows Store</span></span>  
  
 [<span data-ttu-id="7a730-116">适用于应用商店应用的 .NET</span><span class="sxs-lookup"><span data-stu-id="7a730-116">.NET for Store apps</span></span>](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
 <span data-ttu-id="7a730-117">介绍应用商店应用支持的 .NET Framework，可以部署到 Windows 计算机和设备。</span><span class="sxs-lookup"><span data-stu-id="7a730-117">Describes the .NET Framework support for Store apps, which can be deployed to Windows computers and devices.</span></span>  
  
 <span data-ttu-id="7a730-118">[适用于 Windows Phone Silverlight 的 .NET API](http://msdn.microsoft.com/library/windows/apps/xaml/jj207211\(v=vs.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7a730-118">[.NET API for Windows Phone Silverlight](http://msdn.microsoft.com/library/windows/apps/xaml/jj207211\(v=vs.105\).aspx)</span></span>  
 <span data-ttu-id="7a730-119">列出利用 Windows Phone Silverlight 生成应用可使用的 .NET Framework API</span><span class="sxs-lookup"><span data-stu-id="7a730-119">List the .NET Framework APIs you can use for building apps with Windows Phone Silverlight</span></span>  
  
 [<span data-ttu-id="7a730-120">开发多平台应用程序</span><span class="sxs-lookup"><span data-stu-id="7a730-120">Developing for Multiple Platforms</span></span>](../../docs/standard/cross-platform/index.md)  
 <span data-ttu-id="7a730-121">介绍可以针对多个客户端应用类型使用 .NET Framework 的不同方法。</span><span class="sxs-lookup"><span data-stu-id="7a730-121">Describes the different methods you can use the .NET Framework to target multiple client app types.</span></span>  
  
 [<span data-ttu-id="7a730-122">ASP.NET 网站入门</span><span class="sxs-lookup"><span data-stu-id="7a730-122">Get Started with ASP.NET Web Sites</span></span>](http://www.asp.net/get-started/websites)  
 <span data-ttu-id="7a730-123">介绍使用 ASP.NET 开发 Web 应用的方法。</span><span class="sxs-lookup"><span data-stu-id="7a730-123">Describes the ways you can develop web apps using ASP.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a730-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a730-124">See Also</span></span>  
 [<span data-ttu-id="7a730-125">可移植类库</span><span class="sxs-lookup"><span data-stu-id="7a730-125">Portable Class Library</span></span>](../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)  
 [<span data-ttu-id="7a730-126">概述</span><span class="sxs-lookup"><span data-stu-id="7a730-126">Overview</span></span>](../../docs/framework/get-started/overview.md)  
 [<span data-ttu-id="7a730-127">开发指南</span><span class="sxs-lookup"><span data-stu-id="7a730-127">Development Guide</span></span>](../../docs/framework/development-guide.md)  
 [<span data-ttu-id="7a730-128">如何： 创建 Windows 桌面应用程序</span><span class="sxs-lookup"><span data-stu-id="7a730-128">How to: Create a Windows Desktop Application</span></span>](http://msdn.microsoft.com/library/47021403-eaca-4c34-946a-a26c42a64148)  
 [<span data-ttu-id="7a730-129">Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="7a730-129">Windows Service Applications</span></span>](../../docs/framework/windows-services/index.md)
