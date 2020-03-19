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
ms.openlocfilehash: b6b5f47980e7c0c87128b9efb782e637ed7144f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79181635"
---
# <a name="develop-client-applications-with-net-framework"></a><span data-ttu-id="69951-102">使用 .NET Framework 开发客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="69951-102">Develop client applications with .NET Framework</span></span>

<span data-ttu-id="69951-103">可通过多种方法使用 .NET Framework 开发基于 Windows 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="69951-103">There are several ways to develop Windows-based applications with .NET Framework.</span></span> <span data-ttu-id="69951-104">可使用以下任意工具和框架：</span><span class="sxs-lookup"><span data-stu-id="69951-104">You can use any of these tools and frameworks:</span></span>

- [<span data-ttu-id="69951-105">通用 Windows 平台 (UWP)</span><span class="sxs-lookup"><span data-stu-id="69951-105">Universal Windows Platform (UWP)</span></span>](/windows/uwp/)
- [<span data-ttu-id="69951-106">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="69951-106">Windows Presentation Foundation (WPF)</span></span>](./wpf/index.md)
- [<span data-ttu-id="69951-107">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="69951-107">Windows Forms</span></span>](./winforms/index.md)

<span data-ttu-id="69951-108">本节包含的文章说明了如何使用 Windows Presentation Foundation 或 Windows 窗体创建基于 Windows 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="69951-108">This section contains articles that describe how to create Windows-based applications by using Windows Presentation Foundation or Windows Forms.</span></span> <span data-ttu-id="69951-109">但是，还可利用 .NET Framework 创建 Web 应用程序，以及创建可通过 Microsoft Store（UWP 应用）发布的面向计算机或设备的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="69951-109">However, you can also create web applications using .NET Framework and client applications for computers or devices that you make available through Microsoft Store (UWP apps).</span></span>

## <a name="related-sections"></a><span data-ttu-id="69951-110">相关章节</span><span class="sxs-lookup"><span data-stu-id="69951-110">Related sections</span></span>

<span data-ttu-id="69951-111">[通用 Windows 平台](/windows/uwp/)</span><span class="sxs-lookup"><span data-stu-id="69951-111">[Universal Windows Platform](/windows/uwp/)</span></span>\
<span data-ttu-id="69951-112">介绍如何创建可以通过 Microsoft Store 向用户提供的 UWP 应用程序。</span><span class="sxs-lookup"><span data-stu-id="69951-112">Describes how to create UWP applications that you can make available to users through Microsoft Store.</span></span>

<span data-ttu-id="69951-113">[适用于 UWP 应用的 .NET API](/dotnet/api/index?view=dotnet-uwp-10.0)</span><span class="sxs-lookup"><span data-stu-id="69951-113">[.NET API for UWP apps](/dotnet/api/index?view=dotnet-uwp-10.0)</span></span>\
<span data-ttu-id="69951-114">支持 UWP 应用的 .NET 类型参考。</span><span class="sxs-lookup"><span data-stu-id="69951-114">Reference for .NET types that support UWP apps.</span></span>
  
<span data-ttu-id="69951-115">[多平台开发](../standard/cross-platform/index.md)</span><span class="sxs-lookup"><span data-stu-id="69951-115">[Develop for Multiple Platforms](../standard/cross-platform/index.md)</span></span>\
<span data-ttu-id="69951-116">介绍可以针对多个客户端应用类型使用 .NET Framework 的不同方法。</span><span class="sxs-lookup"><span data-stu-id="69951-116">Describes the different methods you can use .NET Framework to target multiple client app types.</span></span>

<span data-ttu-id="69951-117">[ASP.NET 网站入门](https://dotnet.microsoft.com/apps/aspnet/web-apps)</span><span class="sxs-lookup"><span data-stu-id="69951-117">[Get Started with ASP.NET Web Sites](https://dotnet.microsoft.com/apps/aspnet/web-apps)</span></span>\
<span data-ttu-id="69951-118">介绍使用 ASP.NET 开发 Web 应用的方法。</span><span class="sxs-lookup"><span data-stu-id="69951-118">Describes the ways you can develop web apps using ASP.NET.</span></span>

<span data-ttu-id="69951-119">[适用于 Windows Phone Silverlight 的 .NET API](https://docs.microsoft.com/previous-versions/windows/apps/jj207211\(v=vs.105\))</span><span class="sxs-lookup"><span data-stu-id="69951-119">[.NET API for Windows Phone Silverlight](https://docs.microsoft.com/previous-versions/windows/apps/jj207211\(v=vs.105\))</span></span>\
<span data-ttu-id="69951-120">列出使用 Windows Phone Silverlight 构建应用时可使用的 .NET Framework API。</span><span class="sxs-lookup"><span data-stu-id="69951-120">Lists .NET Framework APIs you can use for building apps with Windows Phone Silverlight.</span></span>

## <a name="see-also"></a><span data-ttu-id="69951-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="69951-121">See also</span></span>

- [<span data-ttu-id="69951-122">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="69951-122">.NET Standard</span></span>](../standard/net-standard.md)
- [<span data-ttu-id="69951-123">概述</span><span class="sxs-lookup"><span data-stu-id="69951-123">Overview</span></span>](./get-started/overview.md)
- [<span data-ttu-id="69951-124">开发指南</span><span class="sxs-lookup"><span data-stu-id="69951-124">Development Guide</span></span>](./development-guide.md)
- [<span data-ttu-id="69951-125">Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="69951-125">Windows Service Applications</span></span>](./windows-services/index.md)
