---
title: WPF 主机 (PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: cdd2b451324b1a0edd7aa76494da72623b8326ad
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591264"
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="a80de-102">WPF 主机 (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="a80de-102">WPF Host (PresentationHost.exe)</span></span>
<span data-ttu-id="a80de-103">Windows Presentation Foundation (WPF) 主机 (PresentationHost.exe) 是应用程序，使[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]兼容的浏览器中托管应用程序 (包括[!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)]及更高版本)。</span><span class="sxs-lookup"><span data-stu-id="a80de-103">Windows Presentation Foundation (WPF) Host (PresentationHost.exe) is the application that enables [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications to be hosted in compatible browsers (including [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] and later).</span></span> <span data-ttu-id="a80de-104">默认情况下，Windows Presentation Foundation (WPF) 主机注册为 shell 并[!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)]处理程序的浏览器承载[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]内容，其中包括：</span><span class="sxs-lookup"><span data-stu-id="a80de-104">By default, Windows Presentation Foundation (WPF) Host is registered as the shell and [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] handler for browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content, which includes:</span></span>  
  
- <span data-ttu-id="a80de-105">松散（未编译）[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件 (.xaml)。</span><span class="sxs-lookup"><span data-stu-id="a80de-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
- [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] <span data-ttu-id="a80de-106">(.xbap)。</span><span class="sxs-lookup"><span data-stu-id="a80de-106">(.xbap).</span></span>  
  
 <span data-ttu-id="a80de-107">对于这些类型，Windows Presentation Foundation (WPF) 主机的文件：</span><span class="sxs-lookup"><span data-stu-id="a80de-107">For files of these types, Windows Presentation Foundation (WPF) Host:</span></span>  
  
- <span data-ttu-id="a80de-108">启动注册[!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]处理程序来承载 Windows Presentation Foundation (WPF) 内容。</span><span class="sxs-lookup"><span data-stu-id="a80de-108">Launches the registered [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] handler to host the Windows Presentation Foundation (WPF) content.</span></span>  
  
- <span data-ttu-id="a80de-109">加载的所需的正确版本[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]和 Windows Presentation Foundation (WPF) 程序集。</span><span class="sxs-lookup"><span data-stu-id="a80de-109">Loads the right versions of the required [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] and Windows Presentation Foundation (WPF) assemblies.</span></span>  
  
- <span data-ttu-id="a80de-110">确保部署区域具有适当的权限级别。</span><span class="sxs-lookup"><span data-stu-id="a80de-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="a80de-111">本主题介绍了可以与 PresentationHost.exe 一起使用的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="a80de-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="a80de-112">用法</span><span class="sxs-lookup"><span data-stu-id="a80de-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="a80de-113">参数</span><span class="sxs-lookup"><span data-stu-id="a80de-113">Parameters</span></span>  
  
|<span data-ttu-id="a80de-114">参数</span><span class="sxs-lookup"><span data-stu-id="a80de-114">Parameter</span></span>|<span data-ttu-id="a80de-115">描述</span><span class="sxs-lookup"><span data-stu-id="a80de-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a80de-116">filename</span><span class="sxs-lookup"><span data-stu-id="a80de-116">filename</span></span>|<span data-ttu-id="a80de-117">要激活的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="a80de-117">The path of the file to be activated.</span></span> <span data-ttu-id="a80de-118">也可以为 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a80de-118">Can also be a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>|  
|<span data-ttu-id="a80de-119">-debug</span><span class="sxs-lookup"><span data-stu-id="a80de-119">-debug</span></span>|<span data-ttu-id="a80de-120">激活应用程序时，不要从存储中提交或运行它。</span><span class="sxs-lookup"><span data-stu-id="a80de-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="a80de-121">此参数仅在激活本地文件时才起作用。</span><span class="sxs-lookup"><span data-stu-id="a80de-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="a80de-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="a80de-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="a80de-123">与 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] 值一起使用，以指示 PresentationHost.exe 有一个应用程序应调试，就像从指定的 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] 对其进行部署一样。</span><span class="sxs-lookup"><span data-stu-id="a80de-123">Used with a [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span></span> <span data-ttu-id="a80de-124">此参数可确定部署区域和源站点。</span><span class="sxs-lookup"><span data-stu-id="a80de-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="a80de-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="a80de-125">-embedding</span></span>|<span data-ttu-id="a80de-126">OLE 的必需参数。</span><span class="sxs-lookup"><span data-stu-id="a80de-126">Required by OLE.</span></span> <span data-ttu-id="a80de-127">如果已指定 `-event` 或 `-debug` 参数，则无需指定 `-embedding` 参数，因为该参数已在内部设置。</span><span class="sxs-lookup"><span data-stu-id="a80de-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="a80de-128">-event \<eventname></span><span class="sxs-lookup"><span data-stu-id="a80de-128">-event \<eventname></span></span>|<span data-ttu-id="a80de-129">打开具有此名称的事件，并在 PresentationHost.exe 初始化并准备好承载 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 内容时向该事件发出信号。</span><span class="sxs-lookup"><span data-stu-id="a80de-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="a80de-130">如果打开事件时发生错误（例如该事件尚未创建），则 PresentationHost.exe 将终止。</span><span class="sxs-lookup"><span data-stu-id="a80de-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="a80de-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="a80de-131">-launchApplication \<url></span></span>|<span data-ttu-id="a80de-132">从指定的 URL 启动独立的 [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a80de-132">Launches a standalone [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] application from the specified URL.</span></span> <span data-ttu-id="a80de-133">会应用与 .NET 应用程序有关的 [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] 和 WinINet 安全策略。</span><span class="sxs-lookup"><span data-stu-id="a80de-133">[!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="a80de-134">方案</span><span class="sxs-lookup"><span data-stu-id="a80de-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="a80de-135">Shell 处理程序</span><span class="sxs-lookup"><span data-stu-id="a80de-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="a80de-136">MIME 处理程序</span><span class="sxs-lookup"><span data-stu-id="a80de-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="a80de-137">Visual Studio 调试</span><span class="sxs-lookup"><span data-stu-id="a80de-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="a80de-138">在区域中进行 Visual Studio 调试</span><span class="sxs-lookup"><span data-stu-id="a80de-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="a80de-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="a80de-139">See also</span></span>

- [<span data-ttu-id="a80de-140">安全性</span><span class="sxs-lookup"><span data-stu-id="a80de-140">Security</span></span>](../security-wpf.md)
