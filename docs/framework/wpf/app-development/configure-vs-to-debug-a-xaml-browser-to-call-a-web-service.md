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
ms.openlocfilehash: a4fe68ca4c2d4a58ecf561d17111fdf6a68a9118
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171835"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="fb462-102">如何：将 Visual Studio 配置为通过调试 XAML 浏览器应用程序来调用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="fb462-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] <span data-ttu-id="fb462-103">在 Internet 区域权限集仅限于部分信任安全沙箱中运行。</span><span class="sxs-lookup"><span data-stu-id="fb462-103">run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="fb462-104">此权限集将限制仅 Web 服务位于 Web 服务调用[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]应用程序的源站点。</span><span class="sxs-lookup"><span data-stu-id="fb462-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="fb462-105">当[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]调试从 Visual Studio 2005 中，不过，它不被视为具有相同的源站点的 Web 服务它的引用。</span><span class="sxs-lookup"><span data-stu-id="fb462-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="fb462-106">这会导致安全异常时引发[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]尝试调用 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="fb462-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="fb462-107">但是，Visual Studio 2005[!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)]项目可以配置为模拟有与它进行调试时将调用 Web 服务相同的源站点。</span><span class="sxs-lookup"><span data-stu-id="fb462-107">However, a Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="fb462-108">这允许[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]来安全地调用 Web 服务，而不会导致安全异常。</span><span class="sxs-lookup"><span data-stu-id="fb462-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="fb462-109">配置 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fb462-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="fb462-110">若要配置 Visual Studio 2005 来调试[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]调用 Web 服务：</span><span class="sxs-lookup"><span data-stu-id="fb462-110">To configure Visual Studio 2005 to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>

1.  <span data-ttu-id="fb462-111">在“解决方案资源管理器” 中选择了项目的情况下，在“项目”  菜单上单击“属性” 。</span><span class="sxs-lookup"><span data-stu-id="fb462-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2.  <span data-ttu-id="fb462-112">在中**项目设计器**，单击**调试**选项卡。</span><span class="sxs-lookup"><span data-stu-id="fb462-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3.  <span data-ttu-id="fb462-113">在中**启动操作**部分中，选择**启动外部程序**并输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="fb462-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4.  <span data-ttu-id="fb462-114">在中**启动选项**部分中，输入到以下**命令行参数**文本框中：</span><span class="sxs-lookup"><span data-stu-id="fb462-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     `-debug`  *<span data-ttu-id="fb462-115">filename</span><span class="sxs-lookup"><span data-stu-id="fb462-115">filename</span></span>*

     <span data-ttu-id="fb462-116">*文件名*值 **-调试**参数是.xbap 文件名; 例如：</span><span class="sxs-lookup"><span data-stu-id="fb462-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
>  <span data-ttu-id="fb462-117">这是使用 Visual Studio 2005 创建的解决方案的默认配置[!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)]项目模板。</span><span class="sxs-lookup"><span data-stu-id="fb462-117">This is the default configuration for solutions that are created with the Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>

1.  <span data-ttu-id="fb462-118">在“解决方案资源管理器” 中选择了项目的情况下，在“项目”  菜单上单击“属性” 。</span><span class="sxs-lookup"><span data-stu-id="fb462-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2.  <span data-ttu-id="fb462-119">在中**项目设计器**，单击**调试**选项卡。</span><span class="sxs-lookup"><span data-stu-id="fb462-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3.  <span data-ttu-id="fb462-120">在中**启动选项**部分中，添加以下命令行参数**命令行参数**文本框中：</span><span class="sxs-lookup"><span data-stu-id="fb462-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     `-debugSecurityZoneURL`  *<span data-ttu-id="fb462-121">URL</span><span class="sxs-lookup"><span data-stu-id="fb462-121">URL</span></span>*

     <span data-ttu-id="fb462-122">*URL*值 **-debugSecurityZoneURL**参数是[!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)]你想要模拟不会成为您的应用程序源站点的位置。</span><span class="sxs-lookup"><span data-stu-id="fb462-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="fb462-123">例如，考虑[!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]Web 服务使用以下[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="fb462-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="fb462-124">源站点的[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]为此 Web 服务是：</span><span class="sxs-lookup"><span data-stu-id="fb462-124">The site of origin [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="fb462-125">因此，完整 **-debugSecurityZoneURL**命令行参数和值是：</span><span class="sxs-lookup"><span data-stu-id="fb462-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="fb462-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb462-126">See also</span></span>

- [<span data-ttu-id="fb462-127">WPF 主机 (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="fb462-127">WPF Host (PresentationHost.exe)</span></span>](wpf-host-presentationhost-exe.md)
