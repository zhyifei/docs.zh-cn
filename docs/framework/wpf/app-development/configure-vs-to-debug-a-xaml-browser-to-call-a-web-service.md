---
title: 如何：将 Visual Studio 配置为通过调试 XAML 浏览器应用程序来调用 Web 服务
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: e41dd46e4ddbdcde6448c68b4f9fb2e073baca43
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958691"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="f1155-102">如何：将 Visual Studio 配置为通过调试 XAML 浏览器应用程序来调用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="f1155-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]<span data-ttu-id="f1155-103">在仅限 Internet 区域权限集的部分信任的安全沙盒中运行。</span><span class="sxs-lookup"><span data-stu-id="f1155-103">run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="f1155-104">此权限集将 web 服务调用限制为仅位于[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]应用程序源站点上的 web 服务。</span><span class="sxs-lookup"><span data-stu-id="f1155-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="f1155-105">[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]但是, 当从 Visual Studio 2005 调试时, 它不会被视为与其引用的 Web 服务具有相同的源站点。</span><span class="sxs-lookup"><span data-stu-id="f1155-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="f1155-106">这会导致在[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]尝试调用 Web 服务时引发安全异常。</span><span class="sxs-lookup"><span data-stu-id="f1155-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="f1155-107">但是, 可以将 Visual Studio [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] 2005 项目配置为模拟与调试时所调用的 Web 服务具有相同的源站点。</span><span class="sxs-lookup"><span data-stu-id="f1155-107">However, a Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="f1155-108">这样, 就可以安全地调用 Web 服务, 而不会导致安全异常。 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1155-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="f1155-109">配置 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f1155-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="f1155-110">若要将 Visual Studio 2005 配置为[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]调试调用 Web 服务的, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="f1155-110">To configure Visual Studio 2005 to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>

1. <span data-ttu-id="f1155-111">在“解决方案资源管理器”中选择了项目的情况下，在“项目” 菜单上单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="f1155-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="f1155-112">在**项目设计器**中, 单击 "**调试**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f1155-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="f1155-113">在 "**启动操作**" 部分中, 选择 "**启动外部程序**", 并输入以下内容:</span><span class="sxs-lookup"><span data-stu-id="f1155-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4. <span data-ttu-id="f1155-114">在 "**启动选项**" 部分, 在 "**命令行参数**" 文本框中输入以下内容:</span><span class="sxs-lookup"><span data-stu-id="f1155-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     <span data-ttu-id="f1155-115">`-debug`  *名字*</span><span class="sxs-lookup"><span data-stu-id="f1155-115">`-debug`  *filename*</span></span>

     <span data-ttu-id="f1155-116">**-Debug**参数的*filename*值为 xbap 文件名;例如:</span><span class="sxs-lookup"><span data-stu-id="f1155-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
> <span data-ttu-id="f1155-117">这是通过 Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)]项目模板创建的解决方案的默认配置。</span><span class="sxs-lookup"><span data-stu-id="f1155-117">This is the default configuration for solutions that are created with the Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>

1. <span data-ttu-id="f1155-118">在“解决方案资源管理器”中选择了项目的情况下，在“项目” 菜单上单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="f1155-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="f1155-119">在**项目设计器**中, 单击 "**调试**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f1155-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="f1155-120">在 "**启动选项**" 部分, 将以下命令行参数添加到 "**命令行参数**" 文本框中:</span><span class="sxs-lookup"><span data-stu-id="f1155-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     <span data-ttu-id="f1155-121">`-debugSecurityZoneURL` URL</span><span class="sxs-lookup"><span data-stu-id="f1155-121">`-debugSecurityZoneURL`  *URL*</span></span>

     <span data-ttu-id="f1155-122">**-DebugSecurityZoneURL**参数的*URL*值是要作为应用[!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)]程序源站点模拟的位置的。</span><span class="sxs-lookup"><span data-stu-id="f1155-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="f1155-123">例如, 请考虑[!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]使用 Web 服务的, 其中包含以下[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]内容:</span><span class="sxs-lookup"><span data-stu-id="f1155-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="f1155-124">此 Web 服务的[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]源站点是:</span><span class="sxs-lookup"><span data-stu-id="f1155-124">The site of origin [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="f1155-125">因此, **debugSecurityZoneURL**命令行参数和值为:</span><span class="sxs-lookup"><span data-stu-id="f1155-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="f1155-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1155-126">See also</span></span>

- [<span data-ttu-id="f1155-127">WPF 主机 (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="f1155-127">WPF Host (PresentationHost.exe)</span></span>](wpf-host-presentationhost-exe.md)
