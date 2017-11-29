---
title: "如何：配置 Visual Studio 以调试 XAML 浏览器应用程序来调用 Web 服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5db89cf6220f086d2d71b99f3e6440e584d6a5d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="fee2e-102">如何：配置 Visual Studio 以调试 XAML 浏览器应用程序来调用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="fee2e-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]<span data-ttu-id="fee2e-103">在被限制为 Internet 区域权限集的部分信任安全沙盒中运行。</span><span class="sxs-lookup"><span data-stu-id="fee2e-103"> run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="fee2e-104">此权限集限制仅 Web 服务位于 Web 服务调用[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]应用程序的源站点。</span><span class="sxs-lookup"><span data-stu-id="fee2e-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="fee2e-105">当[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]调试从[!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]，不过它不被视为具有相同的源站点的 Web 服务它的引用。</span><span class="sxs-lookup"><span data-stu-id="fee2e-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)], though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="fee2e-106">此原因安全异常时引发[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]尝试调用 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="fee2e-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="fee2e-107">但是， [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)]项目可以配置为模拟具有在调试时，它调用 Web 服务相同的源站点。</span><span class="sxs-lookup"><span data-stu-id="fee2e-107">However, a [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="fee2e-108">这允许[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]以安全调用 Web 服务，而不会导致安全异常。</span><span class="sxs-lookup"><span data-stu-id="fee2e-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>  
  
## <a name="configuring-visual-studio"></a><span data-ttu-id="fee2e-109">配置 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fee2e-109">Configuring Visual Studio</span></span>  
 <span data-ttu-id="fee2e-110">若要配置[!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]调试[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]调用的 Web 服务：</span><span class="sxs-lookup"><span data-stu-id="fee2e-110">To configure [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>  
  
1.  <span data-ttu-id="fee2e-111">在“解决方案资源管理器” 中选择了项目的情况下，在“项目”  菜单上单击“属性” 。</span><span class="sxs-lookup"><span data-stu-id="fee2e-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="fee2e-112">在**项目设计器**，单击**调试**选项卡。</span><span class="sxs-lookup"><span data-stu-id="fee2e-112">In the **Project Designer**, click the **Debug** tab.</span></span>  
  
3.  <span data-ttu-id="fee2e-113">在**启动操作**部分中，选择**启动外部程序**并输入以下：</span><span class="sxs-lookup"><span data-stu-id="fee2e-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>  
  
     `C:\WINDOWS\System32\PresentationHost.exe`  
  
4.  <span data-ttu-id="fee2e-114">在**启动选项**部分中，输入以下**命令行自变量**文本框：</span><span class="sxs-lookup"><span data-stu-id="fee2e-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>  
  
     <span data-ttu-id="fee2e-115">`-debug`  *文件名*</span><span class="sxs-lookup"><span data-stu-id="fee2e-115">`-debug`  *filename*</span></span>  
  
     <span data-ttu-id="fee2e-116">*Filename*值**-调试**参数是.xbap 文件名; 例如：</span><span class="sxs-lookup"><span data-stu-id="fee2e-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>  
  
     `-debug c:\example.xbap`  
  
> [!NOTE]
>  <span data-ttu-id="fee2e-117">这是使用创建的解决方案的默认配置[!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)][!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)]项目模板。</span><span class="sxs-lookup"><span data-stu-id="fee2e-117">This is the default configuration for solutions that are created with the [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>  
  
1.  <span data-ttu-id="fee2e-118">在“解决方案资源管理器” 中选择了项目的情况下，在“项目”  菜单上单击“属性” 。</span><span class="sxs-lookup"><span data-stu-id="fee2e-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="fee2e-119">在**项目设计器**，单击**调试**选项卡。</span><span class="sxs-lookup"><span data-stu-id="fee2e-119">In the **Project Designer**, click the **Debug** tab.</span></span>  
  
3.  <span data-ttu-id="fee2e-120">在**启动选项**部分中，添加以下命令行参数**命令行自变量**文本框：</span><span class="sxs-lookup"><span data-stu-id="fee2e-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>  
  
     <span data-ttu-id="fee2e-121">`-debugSecurityZoneURL` URL</span><span class="sxs-lookup"><span data-stu-id="fee2e-121">`-debugSecurityZoneURL`  *URL*</span></span>  
  
     <span data-ttu-id="fee2e-122">*URL*值**-debugSecurityZoneURL**参数是[!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)]你想要为你的应用程序的源站点的模拟的位置。</span><span class="sxs-lookup"><span data-stu-id="fee2e-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>  
  
 <span data-ttu-id="fee2e-123">作为示例，请考虑[!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]Web 服务使用以下[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="fee2e-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span></span>  
  
 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`  
  
 <span data-ttu-id="fee2e-124">源站点的[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]对于此 Web 服务是：</span><span class="sxs-lookup"><span data-stu-id="fee2e-124">The site of origin [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] for this Web service is:</span></span>  
  
 `http://services.msdn.microsoft.com`  
  
 <span data-ttu-id="fee2e-125">因此，完成**-debugSecurityZoneURL**命令行参数和值是：</span><span class="sxs-lookup"><span data-stu-id="fee2e-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>  
  
 `-debugSecurityZoneURL http://services.msdn.microsoft.com`  
  
## <a name="see-also"></a><span data-ttu-id="fee2e-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fee2e-126">See Also</span></span>  
 [<span data-ttu-id="fee2e-127">WPF 主机 (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="fee2e-127">WPF Host (PresentationHost.exe)</span></span>](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)
