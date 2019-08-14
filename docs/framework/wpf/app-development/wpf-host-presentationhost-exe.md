---
title: WPF 主机 (PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: eda34c71f5735ae7ea3fcedea3a400e92756243b
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972259"
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="9f4bf-102">WPF 主机 (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="9f4bf-102">WPF Host (PresentationHost.exe)</span></span>
<span data-ttu-id="9f4bf-103">Windows Presentation Foundation (WPF) 宿主 (presentationhost.exe) 是一种应用程序, 它[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]使应用程序可以在兼容的浏览器 (包括 Microsoft Internet Explorer 6 及更高版本) 中承载。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-103">Windows Presentation Foundation (WPF) Host (PresentationHost.exe) is the application that enables [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications to be hosted in compatible browsers (including Microsoft Internet Explorer 6 and later).</span></span> <span data-ttu-id="9f4bf-104">默认情况下, Windows Presentation Foundation (WPF) 主机注册为浏览器承载[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]的内容的 shell 和 MIME 处理程序, 其中包括:</span><span class="sxs-lookup"><span data-stu-id="9f4bf-104">By default, Windows Presentation Foundation (WPF) Host is registered as the shell and MIME handler for browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content, which includes:</span></span>  
  
- <span data-ttu-id="9f4bf-105">松散（未编译）[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件 (.xaml)。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
- [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] <span data-ttu-id="9f4bf-106">(.xbap)。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-106">(.xbap).</span></span>  
  
 <span data-ttu-id="9f4bf-107">对于这些类型的文件, Windows Presentation Foundation (WPF) 主机:</span><span class="sxs-lookup"><span data-stu-id="9f4bf-107">For files of these types, Windows Presentation Foundation (WPF) Host:</span></span>  
  
- <span data-ttu-id="9f4bf-108">启动已注册的 HTML 处理程序以承载 Windows Presentation Foundation (WPF) 内容。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-108">Launches the registered HTML handler to host the Windows Presentation Foundation (WPF) content.</span></span>  
  
- <span data-ttu-id="9f4bf-109">加载所需的公共语言运行时 (CLR) 和 Windows Presentation Foundation (WPF) 程序集的正确版本。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-109">Loads the right versions of the required common language runtime (CLR) and Windows Presentation Foundation (WPF) assemblies.</span></span>  
  
- <span data-ttu-id="9f4bf-110">确保部署区域具有适当的权限级别。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="9f4bf-111">本主题介绍了可以与 PresentationHost.exe 一起使用的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="9f4bf-112">用法</span><span class="sxs-lookup"><span data-stu-id="9f4bf-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="9f4bf-113">参数</span><span class="sxs-lookup"><span data-stu-id="9f4bf-113">Parameters</span></span>  
  
|<span data-ttu-id="9f4bf-114">参数</span><span class="sxs-lookup"><span data-stu-id="9f4bf-114">Parameter</span></span>|<span data-ttu-id="9f4bf-115">描述</span><span class="sxs-lookup"><span data-stu-id="9f4bf-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9f4bf-116">filename</span><span class="sxs-lookup"><span data-stu-id="9f4bf-116">filename</span></span>|<span data-ttu-id="9f4bf-117">要激活的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-117">The path of the file to be activated.</span></span> <span data-ttu-id="9f4bf-118">也可以为 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-118">Can also be a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>|  
|<span data-ttu-id="9f4bf-119">-debug</span><span class="sxs-lookup"><span data-stu-id="9f4bf-119">-debug</span></span>|<span data-ttu-id="9f4bf-120">激活应用程序时，不要从存储中提交或运行它。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="9f4bf-121">此参数仅在激活本地文件时才起作用。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="9f4bf-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="9f4bf-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="9f4bf-123">与 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] 值一起使用，以指示 PresentationHost.exe 有一个应用程序应调试，就像从指定的 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] 对其进行部署一样。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-123">Used with a [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span></span> <span data-ttu-id="9f4bf-124">此参数可确定部署区域和源站点。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="9f4bf-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="9f4bf-125">-embedding</span></span>|<span data-ttu-id="9f4bf-126">OLE 的必需参数。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-126">Required by OLE.</span></span> <span data-ttu-id="9f4bf-127">如果已指定 `-event` 或 `-debug` 参数，则无需指定 `-embedding` 参数，因为该参数已在内部设置。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="9f4bf-128">-event \<eventname></span><span class="sxs-lookup"><span data-stu-id="9f4bf-128">-event \<eventname></span></span>|<span data-ttu-id="9f4bf-129">打开具有此名称的事件，并在 PresentationHost.exe 初始化并准备好承载 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 内容时向该事件发出信号。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="9f4bf-130">如果打开事件时发生错误（例如该事件尚未创建），则 PresentationHost.exe 将终止。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="9f4bf-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="9f4bf-131">-launchApplication \<url></span></span>|<span data-ttu-id="9f4bf-132">从指定的 URL 启动独立的 ClickOnce 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-132">Launches a standalone ClickOnce application from the specified URL.</span></span> <span data-ttu-id="9f4bf-133">应用与 .NET 应用程序有关的 Internet Explorer 和 WinINet 安全策略。</span><span class="sxs-lookup"><span data-stu-id="9f4bf-133">Internet Explorer and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="9f4bf-134">方案</span><span class="sxs-lookup"><span data-stu-id="9f4bf-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="9f4bf-135">Shell 处理程序</span><span class="sxs-lookup"><span data-stu-id="9f4bf-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="9f4bf-136">MIME 处理程序</span><span class="sxs-lookup"><span data-stu-id="9f4bf-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="9f4bf-137">Visual Studio 调试</span><span class="sxs-lookup"><span data-stu-id="9f4bf-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="9f4bf-138">在区域中进行 Visual Studio 调试</span><span class="sxs-lookup"><span data-stu-id="9f4bf-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="9f4bf-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f4bf-139">See also</span></span>

- [<span data-ttu-id="9f4bf-140">安全性</span><span class="sxs-lookup"><span data-stu-id="9f4bf-140">Security</span></span>](../security-wpf.md)
