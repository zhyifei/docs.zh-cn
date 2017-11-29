---
title: "WPF 主机 (PresentationHost.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b7662213d7204675de7e8681b6fc8141f04dd21
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="839b5-102">WPF 主机 (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="839b5-102">WPF Host (PresentationHost.exe)</span></span>
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]<span data-ttu-id="839b5-103"> 主机 (PresentationHost.exe) 是一个应用程序，它使 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 应用程序可在兼容浏览器（包括 [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] 及更高版本）中承载。</span><span class="sxs-lookup"><span data-stu-id="839b5-103"> Host (PresentationHost.exe) is the application that enables [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications to be hosted in compatible browsers (including [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] and later).</span></span> <span data-ttu-id="839b5-104">默认情况下，[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 主机会注册为浏览器承载的 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 内容的 shell 和 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] 处理程序，其中包括：</span><span class="sxs-lookup"><span data-stu-id="839b5-104">By default, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host is registered as the shell and [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] handler for browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content, which includes:</span></span>  
  
-   <span data-ttu-id="839b5-105">松散（未编译）[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件 (.xaml)。</span><span class="sxs-lookup"><span data-stu-id="839b5-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
-   [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]<span data-ttu-id="839b5-106"> (.xbap)。</span><span class="sxs-lookup"><span data-stu-id="839b5-106"> (.xbap).</span></span>  
  
 <span data-ttu-id="839b5-107">对于这些文件类型，[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 主机会：</span><span class="sxs-lookup"><span data-stu-id="839b5-107">For files of these types, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host:</span></span>  
  
-   <span data-ttu-id="839b5-108">启动注册的 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 处理程序来承载 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 内容。</span><span class="sxs-lookup"><span data-stu-id="839b5-108">Launches the registered [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] handler to host the [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] content.</span></span>  
  
-   <span data-ttu-id="839b5-109">加载所需 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 和 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 程序集的正确版本。</span><span class="sxs-lookup"><span data-stu-id="839b5-109">Loads the right versions of the required [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] and [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] assemblies.</span></span>  
  
-   <span data-ttu-id="839b5-110">确保部署区域具有适当的权限级别。</span><span class="sxs-lookup"><span data-stu-id="839b5-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="839b5-111">本主题介绍了可以与 PresentationHost.exe 一起使用的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="839b5-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="839b5-112">用法</span><span class="sxs-lookup"><span data-stu-id="839b5-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="839b5-113">参数</span><span class="sxs-lookup"><span data-stu-id="839b5-113">Parameters</span></span>  
  
|<span data-ttu-id="839b5-114">参数</span><span class="sxs-lookup"><span data-stu-id="839b5-114">Parameter</span></span>|<span data-ttu-id="839b5-115">描述</span><span class="sxs-lookup"><span data-stu-id="839b5-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="839b5-116">filename</span><span class="sxs-lookup"><span data-stu-id="839b5-116">filename</span></span>|<span data-ttu-id="839b5-117">要激活的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="839b5-117">The path of the file to be activated.</span></span> <span data-ttu-id="839b5-118">也可以为 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="839b5-118">Can also be a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>|  
|<span data-ttu-id="839b5-119">-debug</span><span class="sxs-lookup"><span data-stu-id="839b5-119">-debug</span></span>|<span data-ttu-id="839b5-120">激活应用程序时，不要从存储中提交或运行它。</span><span class="sxs-lookup"><span data-stu-id="839b5-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="839b5-121">此参数仅在激活本地文件时才起作用。</span><span class="sxs-lookup"><span data-stu-id="839b5-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="839b5-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="839b5-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="839b5-123">与 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] 值一起使用，以指示 PresentationHost.exe 有一个应用程序应调试，就像从指定的 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] 对其进行部署一样。</span><span class="sxs-lookup"><span data-stu-id="839b5-123">Used with a [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span></span> <span data-ttu-id="839b5-124">此参数可确定部署区域和源站点。</span><span class="sxs-lookup"><span data-stu-id="839b5-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="839b5-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="839b5-125">-embedding</span></span>|<span data-ttu-id="839b5-126">OLE 的必需参数。</span><span class="sxs-lookup"><span data-stu-id="839b5-126">Required by OLE.</span></span> <span data-ttu-id="839b5-127">如果已指定 `-event` 或 `-debug` 参数，则无需指定 `-embedding` 参数，因为该参数已在内部设置。</span><span class="sxs-lookup"><span data-stu-id="839b5-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="839b5-128">-event \<eventname></span><span class="sxs-lookup"><span data-stu-id="839b5-128">-event \<eventname></span></span>|<span data-ttu-id="839b5-129">打开具有此名称的事件，并在 PresentationHost.exe 初始化并准备好承载 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 内容时向该事件发出信号。</span><span class="sxs-lookup"><span data-stu-id="839b5-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="839b5-130">如果打开事件时发生错误（例如该事件尚未创建），则 PresentationHost.exe 将终止。</span><span class="sxs-lookup"><span data-stu-id="839b5-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="839b5-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="839b5-131">-launchApplication \<url></span></span>|<span data-ttu-id="839b5-132">从指定的 URL 启动独立的 [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] 应用程序。</span><span class="sxs-lookup"><span data-stu-id="839b5-132">Launches a standalone [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] application from the specified URL.</span></span> <span data-ttu-id="839b5-133">会应用与 .NET 应用程序有关的 [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] 和 WinINet 安全策略。</span><span class="sxs-lookup"><span data-stu-id="839b5-133">[!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="839b5-134">方案</span><span class="sxs-lookup"><span data-stu-id="839b5-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="839b5-135">Shell 处理程序</span><span class="sxs-lookup"><span data-stu-id="839b5-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="839b5-136">MIME 处理程序</span><span class="sxs-lookup"><span data-stu-id="839b5-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="839b5-137">Visual Studio 调试</span><span class="sxs-lookup"><span data-stu-id="839b5-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="839b5-138">在区域中进行 Visual Studio 调试</span><span class="sxs-lookup"><span data-stu-id="839b5-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="839b5-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="839b5-139">See Also</span></span>  
 [<span data-ttu-id="839b5-140">安全性</span><span class="sxs-lookup"><span data-stu-id="839b5-140">Security</span></span>](../../../../docs/framework/wpf/security-wpf.md)
