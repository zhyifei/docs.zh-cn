---
title: 如何：配置 Visual Studio 以调试 XAML 浏览器应用程序来调用 Web 服务
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: 8ec278f2bc66d9b40786123af684f6468b6a9d83
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005669"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="2044e-102">如何：配置 Visual Studio 以调试 XAML 浏览器应用程序来调用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="2044e-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] <span data-ttu-id="2044e-103">在部分信任的安全沙盒中运行，该沙箱限制为 Internet 区域权限集。</span><span class="sxs-lookup"><span data-stu-id="2044e-103">run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="2044e-104">此权限集将 Web 服务调用限制为仅位于 @no__t 的应用程序源站点上的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="2044e-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="2044e-105">不过，如果从 Visual Studio 2005 调试 @no__t 0，则不会被视为具有与其引用的 Web 服务相同的源站点。</span><span class="sxs-lookup"><span data-stu-id="2044e-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="2044e-106">这会导致在 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 尝试调用 Web 服务时引发安全异常。</span><span class="sxs-lookup"><span data-stu-id="2044e-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="2044e-107">但是，可以将 Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] 项目配置为模拟在调试时与它调用的 Web 服务具有相同的源站点。</span><span class="sxs-lookup"><span data-stu-id="2044e-107">However, a Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="2044e-108">这允许 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 安全地调用 Web 服务，而不会导致安全异常。</span><span class="sxs-lookup"><span data-stu-id="2044e-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="2044e-109">配置 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2044e-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="2044e-110">若要将 Visual Studio 2005 配置为调试调用 Web 服务的 @no__t，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2044e-110">To configure Visual Studio 2005 to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>

1. <span data-ttu-id="2044e-111">在“解决方案资源管理器”中选择了项目的情况下，在“项目” 菜单上单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="2044e-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="2044e-112">在**项目设计器**中，单击 "**调试**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2044e-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="2044e-113">在 "**启动操作**" 部分中，选择 "**启动外部程序**"，并输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="2044e-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4. <span data-ttu-id="2044e-114">在 "**启动选项**" 部分，在 "**命令行参数**" 文本框中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="2044e-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     <span data-ttu-id="2044e-115">`-debug`  *filename*</span><span class="sxs-lookup"><span data-stu-id="2044e-115">`-debug`  *filename*</span></span>

     <span data-ttu-id="2044e-116">**-Debug**参数的*filename*值为 xbap 文件名;例如：</span><span class="sxs-lookup"><span data-stu-id="2044e-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
> <span data-ttu-id="2044e-117">这是通过 Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] 项目模板创建的解决方案的默认配置。</span><span class="sxs-lookup"><span data-stu-id="2044e-117">This is the default configuration for solutions that are created with the Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>

1. <span data-ttu-id="2044e-118">在“解决方案资源管理器”中选择了项目的情况下，在“项目” 菜单上单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="2044e-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="2044e-119">在**项目设计器**中，单击 "**调试**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2044e-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="2044e-120">在 "**启动选项**" 部分，将以下命令行参数添加到 "**命令行参数**" 文本框中：</span><span class="sxs-lookup"><span data-stu-id="2044e-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     <span data-ttu-id="2044e-121">`-debugSecurityZoneURL` URL</span><span class="sxs-lookup"><span data-stu-id="2044e-121">`-debugSecurityZoneURL`  *URL*</span></span>

     <span data-ttu-id="2044e-122">**-DebugSecurityZoneURL**参数的*URL*值是你要模拟为你的应用程序源站点的位置 [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2044e-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="2044e-123">作为示例，请考虑使用具有以下 URL 的 Web 服务的 [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]：</span><span class="sxs-lookup"><span data-stu-id="2044e-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following URL:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="2044e-124">此 Web 服务的源网站 URL 为：</span><span class="sxs-lookup"><span data-stu-id="2044e-124">The site of origin URL for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="2044e-125">因此， **debugSecurityZoneURL**命令行参数和值为：</span><span class="sxs-lookup"><span data-stu-id="2044e-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="2044e-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="2044e-126">See also</span></span>

- [<span data-ttu-id="2044e-127">WPF 主机 (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="2044e-127">WPF Host (PresentationHost.exe)</span></span>](wpf-host-presentationhost-exe.md)
