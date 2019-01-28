---
title: 使用 .NET Framework 开发基于 Windows 的客户端应用程序
ms.date: 01/09/2018
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
ms.openlocfilehash: 68d9365e6aed247770eb250f5a2e296b710febc2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671286"
---
# <a name="developing-client-applications-with-the-net-framework"></a><span data-ttu-id="fe089-102">使用 .NET Framework 开发客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="fe089-102">Developing client applications with the .NET Framework</span></span>

<span data-ttu-id="fe089-103">可通过多种方法使用 .NET Framework 开发基于 Windows 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fe089-103">There are several ways to develop Windows-based applications with the .NET Framework.</span></span> <span data-ttu-id="fe089-104">可使用以下任意工具和框架：</span><span class="sxs-lookup"><span data-stu-id="fe089-104">You can use any of these tools and frameworks:</span></span> 

* [<span data-ttu-id="fe089-105">通用 Windows 平台 (UWP)</span><span class="sxs-lookup"><span data-stu-id="fe089-105">Universal Windows Platform (UWP)</span></span>](https://developer.microsoft.com/windows/apps)
* [<span data-ttu-id="fe089-106">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="fe089-106">Windows Presentation Foundation (WPF)</span></span>](../../docs/framework/wpf/index.md)
* [<span data-ttu-id="fe089-107">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="fe089-107">Windows Forms</span></span>](../../docs/framework/winforms/index.md)

<span data-ttu-id="fe089-108">本节包含的主题说明了如何使用 Windows Presentation Foundation 或 Windows 窗体创建基于 Windows 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fe089-108">This section contains topics that describe how to create Windows-based applications by using Windows Presentation Foundation or by using Windows Forms.</span></span> <span data-ttu-id="fe089-109">但是，还可利用 .NET Framework 创建 Web 应用程序，以及创建可通过 Microsoft Store 发布的面向计算机或设备的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="fe089-109">However, you can also create web applications using the .NET Framework, and client applications for computers or devices that you make available through the Microsoft Store.</span></span>
 
## <a name="in-this-section"></a><span data-ttu-id="fe089-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="fe089-110">In this section</span></span>

[<span data-ttu-id="fe089-111">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="fe089-111">Windows Presentation Foundation</span></span>](../../docs/framework/wpf/index.md)  
<span data-ttu-id="fe089-112">提供有关使用 WPF 开发和部署应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="fe089-112">Provides information about developing applications by using WPF.</span></span>

[<span data-ttu-id="fe089-113">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="fe089-113">Windows Forms</span></span>](../../docs/framework/winforms/index.md)  
<span data-ttu-id="fe089-114">提供有关使用 Windows 窗体开发和部署应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="fe089-114">Provides information about developing applications by using Windows Forms.</span></span>

[<span data-ttu-id="fe089-115">常用的客户端技术</span><span class="sxs-lookup"><span data-stu-id="fe089-115">Common Client Technologies</span></span>](../../docs/framework/common-client-technologies/index.md)  
<span data-ttu-id="fe089-116">提供有关在开发客户端应用程序时可使用的其他技术的信息。</span><span class="sxs-lookup"><span data-stu-id="fe089-116">Provides information about additional technologies that can be used when developing client applications.</span></span>

## <a name="related-sections"></a><span data-ttu-id="fe089-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="fe089-117">Related sections</span></span>

[<span data-ttu-id="fe089-118">通用 Windows 平台</span><span class="sxs-lookup"><span data-stu-id="fe089-118">Universal Windows Platform</span></span>](https://developer.microsoft.com/windows/apps)  
<span data-ttu-id="fe089-119">介绍如何创建可通过 Windows 应用商店向用户提供的 Windows 10 应用。</span><span class="sxs-lookup"><span data-stu-id="fe089-119">Describes how to create applications for Windows 10 that you can make available to users through the Windows Store.</span></span>

[<span data-ttu-id="fe089-120">适用于 UWP 应用的 .NET</span><span class="sxs-lookup"><span data-stu-id="fe089-120">.NET for UWP apps</span></span>](https://msdn.microsoft.com/library/windows/apps/mt185501.aspx)  
<span data-ttu-id="fe089-121">介绍应用商店应用支持的 .NET Framework，可以部署到 Windows 计算机和设备。</span><span class="sxs-lookup"><span data-stu-id="fe089-121">Describes the .NET Framework support for Store apps, which can be deployed to Windows computers and devices.</span></span>

<span data-ttu-id="fe089-122">[适用于 Windows Phone Silverlight 的 .NET API](https://docs.microsoft.com/previous-versions/windows/apps/jj207211\(v=vs.105\))</span><span class="sxs-lookup"><span data-stu-id="fe089-122">[.NET API for Windows Phone Silverlight](https://docs.microsoft.com/previous-versions/windows/apps/jj207211\(v=vs.105\))</span></span>  
<span data-ttu-id="fe089-123">列出使用 Windows Phone Silverlight 构建应用时可使用的 .NET Framework API。</span><span class="sxs-lookup"><span data-stu-id="fe089-123">Lists the .NET Framework APIs you can use for building apps with Windows Phone Silverlight.</span></span>
  
[<span data-ttu-id="fe089-124">开发多平台应用程序</span><span class="sxs-lookup"><span data-stu-id="fe089-124">Developing for Multiple Platforms</span></span>](../../docs/standard/cross-platform/index.md)  
<span data-ttu-id="fe089-125">介绍可以针对多个客户端应用类型使用 .NET Framework 的不同方法。</span><span class="sxs-lookup"><span data-stu-id="fe089-125">Describes the different methods you can use the .NET Framework to target multiple client app types.</span></span>

[<span data-ttu-id="fe089-126">ASP.NET 网站入门</span><span class="sxs-lookup"><span data-stu-id="fe089-126">Get Started with ASP.NET Web Sites</span></span>](https://www.asp.net/get-started/websites)  
<span data-ttu-id="fe089-127">介绍使用 ASP.NET 开发 Web 应用的方法。</span><span class="sxs-lookup"><span data-stu-id="fe089-127">Describes the ways you can develop web apps using ASP.NET.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe089-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe089-128">See also</span></span>

- [<span data-ttu-id="fe089-129">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="fe089-129">.NET Standard</span></span>](../../docs/standard/net-standard.md)
- [<span data-ttu-id="fe089-130">概述</span><span class="sxs-lookup"><span data-stu-id="fe089-130">Overview</span></span>](../../docs/framework/get-started/overview.md)
- [<span data-ttu-id="fe089-131">开发指南</span><span class="sxs-lookup"><span data-stu-id="fe089-131">Development Guide</span></span>](../../docs/framework/development-guide.md)
- [<span data-ttu-id="fe089-132">Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="fe089-132">Windows Service Applications</span></span>](../../docs/framework/windows-services/index.md)
