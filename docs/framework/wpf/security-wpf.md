---
title: 安全性
ms.date: 03/30/2017
helpviewer_keywords:
- XAML files [WPF], sandbox behavior
- browser-hosted application security [WPF]
- application security [WPF]
- navigation security [WPF]
- loose XAML files [WPF], sandbox behavior
- WPF security [WPF]
- WebBrowser control [WPF], security
- feature controls [WPF], security
- XBAP security [WPF]
- Internet Explorer security settings [WPF]
ms.assetid: ee1baea0-3611-4e36-9ad6-fcd5205376fb
ms.openlocfilehash: e0a56dcbf8d151fcb0d4f6271ecba15c0ff955a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174610"
---
# <a name="security-wpf"></a><span data-ttu-id="799e0-102">安全性 (WPF)</span><span class="sxs-lookup"><span data-stu-id="799e0-102">Security (WPF)</span></span>
<a name="introduction"></a><span data-ttu-id="799e0-103">在开发 Windows 演示文稿基础 （WPF） 独立和浏览器托管的应用程序时，必须考虑安全模型。</span><span class="sxs-lookup"><span data-stu-id="799e0-103">When developing Windows Presentation Foundation (WPF) standalone and browser-hosted applications, you must consider the security model.</span></span> <span data-ttu-id="799e0-104">WPF 独立应用程序以不受限制的权限（CAS**完全信任**权限集）执行，无论是使用 Windows 安装程序 （.msi）、XCopy 还是 ClickOnce 部署。</span><span class="sxs-lookup"><span data-stu-id="799e0-104">WPF standalone applications execute with unrestricted permissions ( CAS**FullTrust** permission set), whether deployed using Windows Installer (.msi), XCopy, or ClickOnce.</span></span> <span data-ttu-id="799e0-105">不支持使用 ClickOnce 部署部分信任的独立 WPF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="799e0-105">Deploying partial-trust, standalone WPF applications with ClickOnce is unsupported.</span></span> <span data-ttu-id="799e0-106">但是，完全信任的主机应用程序可以使用 .NET 框架外<xref:System.AppDomain>接程序模型创建部分信任。</span><span class="sxs-lookup"><span data-stu-id="799e0-106">However, a full-trust host application can create a partial-trust <xref:System.AppDomain> using the .NET Framework Add-in model.</span></span> <span data-ttu-id="799e0-107">有关详细信息，请参阅[WPF 加载项概述](./app-development/wpf-add-ins-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="799e0-107">For more information, see [WPF Add-Ins Overview](./app-development/wpf-add-ins-overview.md).</span></span>  
  
 <span data-ttu-id="799e0-108">WPF浏览器托管的应用程序由 Windows Internet 资源管理器或 Firefox 托管，可以是 XAML 浏览器应用程序 （XBAPs） 或松散[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)]文档 有关详细信息，请参阅[WPF XAML 浏览器应用程序概述](./app-development/wpf-xaml-browser-applications-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="799e0-108">WPF browser-hosted applications are hosted by Windows Internet Explorer or Firefox, and can be either XAML browser applications (XBAPs) or loose [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] documents For more information, see [WPF XAML Browser Applications Overview](./app-development/wpf-xaml-browser-applications-overview.md).</span></span>  
  
 <span data-ttu-id="799e0-109">默认情况下，WPF 浏览器托管的应用程序在部分信任安全沙盒中执行，该沙盒仅限于默认的 CAS**Internet**区域权限集。</span><span class="sxs-lookup"><span data-stu-id="799e0-109">WPF browser-hosted applications execute within a partial trust security sandbox, by default, which is limited to the default CAS**Internet** zone permission set.</span></span> <span data-ttu-id="799e0-110">这将有效地将 WPF 浏览器托管的应用程序与客户端计算机隔离，就像您希望将典型的 Web 应用程序隔离一样。</span><span class="sxs-lookup"><span data-stu-id="799e0-110">This effectively isolates WPF browser-hosted applications from the client computer in the same way that you would expect typical Web applications to be isolated.</span></span> <span data-ttu-id="799e0-111">XBAP 最高可以将权限提升到“完全信任”，具体取决于部署 URL 的安全区域和客户端的安全配置。</span><span class="sxs-lookup"><span data-stu-id="799e0-111">An XBAP can elevate privileges, up to Full Trust, depending on the security zone of the deployment URL and the client's security configuration.</span></span> <span data-ttu-id="799e0-112">有关详细信息，请参阅[WPF 部分信任安全](wpf-partial-trust-security.md)。</span><span class="sxs-lookup"><span data-stu-id="799e0-112">For more information, see [WPF Partial Trust Security](wpf-partial-trust-security.md).</span></span>  
  
 <span data-ttu-id="799e0-113">本主题讨论 Windows 演示文稿基础 （WPF） 独立和浏览器托管应用程序的安全模型。</span><span class="sxs-lookup"><span data-stu-id="799e0-113">This topic discusses the security model for Windows Presentation Foundation (WPF) standalone and browser-hosted applications.</span></span>  
  
 <span data-ttu-id="799e0-114">本主题包含以下各节：</span><span class="sxs-lookup"><span data-stu-id="799e0-114">This topic contains the following sections:</span></span>  
  
- [<span data-ttu-id="799e0-115">安全导航</span><span class="sxs-lookup"><span data-stu-id="799e0-115">Safe Navigation</span></span>](#SafeTopLevelNavigation)  
  
- [<span data-ttu-id="799e0-116">Web 浏览软件安全设置</span><span class="sxs-lookup"><span data-stu-id="799e0-116">Web Browsing Software Security Settings</span></span>](#InternetExplorerSecuritySettings)  
  
- [<span data-ttu-id="799e0-117">WebBrowser 控件和功能控件</span><span class="sxs-lookup"><span data-stu-id="799e0-117">WebBrowser Control and Feature Controls</span></span>](#webbrowser_control_and_feature_controls)  
  
- [<span data-ttu-id="799e0-118">对部分受信任的客户端应用程序禁用 APTCA 程序集</span><span class="sxs-lookup"><span data-stu-id="799e0-118">Disabling APTCA Assemblies for Partially Trusted Client Applications</span></span>](#APTCA)  
  
- [<span data-ttu-id="799e0-119">宽松 XAML 文件的沙盒行为</span><span class="sxs-lookup"><span data-stu-id="799e0-119">Sandbox Behavior for Loose XAML Files</span></span>](#LooseContentSandboxing)  
  
- [<span data-ttu-id="799e0-120">用于开发可提高安全性的 WPF 应用程序的资源</span><span class="sxs-lookup"><span data-stu-id="799e0-120">Resources for Developing WPF Applications that Promote Security</span></span>](#BestPractices)  
  
<a name="SafeTopLevelNavigation"></a>
## <a name="safe-navigation"></a><span data-ttu-id="799e0-121">安全导航</span><span class="sxs-lookup"><span data-stu-id="799e0-121">Safe Navigation</span></span>  
 <span data-ttu-id="799e0-122">对于 XBAP，WPF 区分两种类型的导航：应用程序和浏览器。</span><span class="sxs-lookup"><span data-stu-id="799e0-122">For XBAPs, WPF distinguishes two types of navigation: application and browser.</span></span>  
  
 <span data-ttu-id="799e0-123">应用程序导航\*\* 是指在浏览器托管的应用程序内的内容项之间进行导航。</span><span class="sxs-lookup"><span data-stu-id="799e0-123">*Application navigation* is navigation between items of content within an application that is hosted by a browser.</span></span> <span data-ttu-id="799e0-124">浏览器导航\*\* 是指可更改浏览器自身的内容和位置 URL 的导航。</span><span class="sxs-lookup"><span data-stu-id="799e0-124">*Browser navigation* is navigation that changes the content and location URL of a browser itself.</span></span> <span data-ttu-id="799e0-125">应用程序导航（通常为 XAML）和浏览器导航（通常 HTML）之间的关系如下图所示：</span><span class="sxs-lookup"><span data-stu-id="799e0-125">The relationship between application navigation (typically XAML) and browser navigation (typically HTML) is shown in the following illustration:</span></span>
  
 ![应用程序导航和浏览器导航之间的关系。](./media/security-wpf/application-browser-navigation-relationship.png)  
  
 <span data-ttu-id="799e0-127">XBAP 导航到的内容类型主要取决于是否使用应用程序导航或浏览器导航。</span><span class="sxs-lookup"><span data-stu-id="799e0-127">The type of content that is considered safe for an XBAP to navigate to is primarily determined by whether application navigation or browser navigation is used.</span></span>  
  
<a name="Application_Navigation_Security"></a>
### <a name="application-navigation-security"></a><span data-ttu-id="799e0-128">应用程序导航安全性</span><span class="sxs-lookup"><span data-stu-id="799e0-128">Application Navigation Security</span></span>  
 <span data-ttu-id="799e0-129">如果可以使用包 URI 进行标识，则应用程序导航被视为安全，该 URI 支持四种类型的内容：</span><span class="sxs-lookup"><span data-stu-id="799e0-129">Application navigation is considered safe if it can be identified with a pack URI, which supports four types of content:</span></span>  
  
|<span data-ttu-id="799e0-130">内容类型</span><span class="sxs-lookup"><span data-stu-id="799e0-130">Content Type</span></span>|<span data-ttu-id="799e0-131">说明</span><span class="sxs-lookup"><span data-stu-id="799e0-131">Description</span></span>|<span data-ttu-id="799e0-132">URI 示例</span><span class="sxs-lookup"><span data-stu-id="799e0-132">URI Example</span></span>|  
|------------------|-----------------|-----------------|  
|<span data-ttu-id="799e0-133">资源</span><span class="sxs-lookup"><span data-stu-id="799e0-133">Resource</span></span>|<span data-ttu-id="799e0-134">添加到具有生成类型的**资源**的项目的文件。</span><span class="sxs-lookup"><span data-stu-id="799e0-134">Files that are added to a project with a build type of **Resource**.</span></span>|`pack://application:,,,/MyResourceFile.xaml`|  
|<span data-ttu-id="799e0-135">内容</span><span class="sxs-lookup"><span data-stu-id="799e0-135">Content</span></span>|<span data-ttu-id="799e0-136">添加到具有生成**类型内容**的项目的文件。</span><span class="sxs-lookup"><span data-stu-id="799e0-136">Files that are added to a project with a build type of **Content**.</span></span>|`pack://application:,,,/MyContentFile.xaml`|  
|<span data-ttu-id="799e0-137">源站点</span><span class="sxs-lookup"><span data-stu-id="799e0-137">Site of origin</span></span>|<span data-ttu-id="799e0-138">添加到生成类型的 **"无"** 的项目的文件。</span><span class="sxs-lookup"><span data-stu-id="799e0-138">Files that are added to a project with a build type of **None**.</span></span>|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|<span data-ttu-id="799e0-139">应用程序代码</span><span class="sxs-lookup"><span data-stu-id="799e0-139">Application code</span></span>|<span data-ttu-id="799e0-140">具有已编译代码隐藏的 XAML 资源。</span><span class="sxs-lookup"><span data-stu-id="799e0-140">XAML resources that have a compiled code-behind.</span></span><br /><br /> <span data-ttu-id="799e0-141">-或-</span><span class="sxs-lookup"><span data-stu-id="799e0-141">-or-</span></span><br /><br /> <span data-ttu-id="799e0-142">添加到具有生成类型的**Page**的项目的 XAML 文件。</span><span class="sxs-lookup"><span data-stu-id="799e0-142">XAML files that are added to a project with a build type of **Page**.</span></span>|<span data-ttu-id="799e0-143">`pack://application:,,,/MyResourceFile` `.xaml`</span><span class="sxs-lookup"><span data-stu-id="799e0-143">`pack://application:,,,/MyResourceFile` `.xaml`</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="799e0-144">有关应用程序数据文件和打包 URI 的详细信息，请参阅[WPF 应用程序资源、内容和数据文件](./app-development/wpf-application-resource-content-and-data-files.md)。</span><span class="sxs-lookup"><span data-stu-id="799e0-144">For more information about application data files and pack URIs, see [WPF Application Resource, Content, and Data Files](./app-development/wpf-application-resource-content-and-data-files.md).</span></span>  
  
 <span data-ttu-id="799e0-145">可以由用户导航到这些内容类型的文件，也可以通过编程方式导航到这些内容类型的文件：</span><span class="sxs-lookup"><span data-stu-id="799e0-145">Files of these content types can be navigated to by either the user or programmatically:</span></span>  
  
- <span data-ttu-id="799e0-146">**用户导航**。</span><span class="sxs-lookup"><span data-stu-id="799e0-146">**User Navigation**.</span></span> <span data-ttu-id="799e0-147">用户通过单击<xref:System.Windows.Documents.Hyperlink>元素进行导航。</span><span class="sxs-lookup"><span data-stu-id="799e0-147">The user navigates by clicking a <xref:System.Windows.Documents.Hyperlink> element.</span></span>  
  
- <span data-ttu-id="799e0-148">**编程导航**。</span><span class="sxs-lookup"><span data-stu-id="799e0-148">**Programmatic Navigation**.</span></span> <span data-ttu-id="799e0-149">应用程序导航时不涉及用户，例如，通过设置<xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="799e0-149">The application navigates without involving the user, for example, by setting the <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType> property.</span></span>  
  
<a name="Browser_Navigation_Security"></a>
### <a name="browser-navigation-security"></a><span data-ttu-id="799e0-150">浏览器导航安全性</span><span class="sxs-lookup"><span data-stu-id="799e0-150">Browser Navigation Security</span></span>  
 <span data-ttu-id="799e0-151">浏览器导航仅在以下条件下被视为安全：</span><span class="sxs-lookup"><span data-stu-id="799e0-151">Browser navigation is considered safe only under the following conditions:</span></span>  
  
- <span data-ttu-id="799e0-152">**用户导航**。</span><span class="sxs-lookup"><span data-stu-id="799e0-152">**User Navigation**.</span></span> <span data-ttu-id="799e0-153">用户通过单击<xref:System.Windows.Documents.Hyperlink>主<xref:System.Windows.Navigation.NavigationWindow>元素中的元素而不是嵌套<xref:System.Windows.Controls.Frame>中进行导航。</span><span class="sxs-lookup"><span data-stu-id="799e0-153">The user navigates by clicking a <xref:System.Windows.Documents.Hyperlink> element that is within the main <xref:System.Windows.Navigation.NavigationWindow>, not in a nested <xref:System.Windows.Controls.Frame>.</span></span>  
  
- <span data-ttu-id="799e0-154">**区域**。</span><span class="sxs-lookup"><span data-stu-id="799e0-154">**Zone**.</span></span> <span data-ttu-id="799e0-155">要导航到的内容位于 Internet 或本地 Intranet 上。</span><span class="sxs-lookup"><span data-stu-id="799e0-155">The content being navigated to is located on the Internet or the local intranet.</span></span>  
  
- <span data-ttu-id="799e0-156">**协议**。</span><span class="sxs-lookup"><span data-stu-id="799e0-156">**Protocol**.</span></span> <span data-ttu-id="799e0-157">**file**正在使用的协议是**http\*\*\*\*http、https、** 文件或**mailto**。</span><span class="sxs-lookup"><span data-stu-id="799e0-157">The protocol being used is either **http**, **https**, **file**, or **mailto**.</span></span>  
  
 <span data-ttu-id="799e0-158">如果 XBAP 尝试以不符合这些条件的方式导航到内容，则引发 。 <xref:System.Security.SecurityException></span><span class="sxs-lookup"><span data-stu-id="799e0-158">If an XBAP attempts to navigate to content in a manner that does not comply with these conditions, a <xref:System.Security.SecurityException> is thrown.</span></span>  
  
<a name="InternetExplorerSecuritySettings"></a>
## <a name="web-browsing-software-security-settings"></a><span data-ttu-id="799e0-159">Web 浏览软件安全设置</span><span class="sxs-lookup"><span data-stu-id="799e0-159">Web Browsing Software Security Settings</span></span>  
 <span data-ttu-id="799e0-160">计算机上的安全设置决定了任何 Web 浏览软件被授予的访问权限。</span><span class="sxs-lookup"><span data-stu-id="799e0-160">The security settings on your computer determine the access that any Web browsing software is granted.</span></span> <span data-ttu-id="799e0-161">Web 浏览软件包括使用[WinINet](/windows/win32/wininet/portal)或[UrlMon](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa767916(v=vs.85)) API 的任何应用程序或组件，包括 Internet 资源管理器和演示Host.exe。</span><span class="sxs-lookup"><span data-stu-id="799e0-161">Web browsing software includes any application or component that uses the [WinINet](/windows/win32/wininet/portal) or [UrlMon](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa767916(v=vs.85)) APIs, including Internet Explorer and PresentationHost.exe.</span></span>  
  
 <span data-ttu-id="799e0-162">Internet Explorer 提供了一种机制，通过该机制可以配置允许由 Internet Explorer 执行的功能，包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="799e0-162">Internet Explorer provides a mechanism by which you can configure the functionality that is allowed to be executed by or from Internet Explorer, including the following:</span></span>  
  
- <span data-ttu-id="799e0-163">.NET 框架依赖组件</span><span class="sxs-lookup"><span data-stu-id="799e0-163">.NET Framework-reliant components</span></span>  
  
- <span data-ttu-id="799e0-164">ActiveX 控件和插件</span><span class="sxs-lookup"><span data-stu-id="799e0-164">ActiveX controls and plug-ins</span></span>  
  
- <span data-ttu-id="799e0-165">下载</span><span class="sxs-lookup"><span data-stu-id="799e0-165">Downloads</span></span>  
  
- <span data-ttu-id="799e0-166">脚本编写</span><span class="sxs-lookup"><span data-stu-id="799e0-166">Scripting</span></span>  
  
- <span data-ttu-id="799e0-167">用户身份验证</span><span class="sxs-lookup"><span data-stu-id="799e0-167">User Authentication</span></span>  
  
 <span data-ttu-id="799e0-168">以这种方式保护的功能集合按区域配置，用于**Internet、Intranet、\*\*\*\*受信任的站点**和**受限站点**区域。 **Internet**</span><span class="sxs-lookup"><span data-stu-id="799e0-168">The collection of functionality that can be secured in this way is configured on a per-zone basis for the **Internet**, **Intranet**, **Trusted Sites**, and **Restricted Sites** zones.</span></span> <span data-ttu-id="799e0-169">以下步骤描述如何配置安全设置：</span><span class="sxs-lookup"><span data-stu-id="799e0-169">The following steps describe how to configure your security settings:</span></span>  
  
1. <span data-ttu-id="799e0-170">打开“控制面板”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="799e0-170">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="799e0-171">点击**网络和互联网**，然后单击**互联网选项**。</span><span class="sxs-lookup"><span data-stu-id="799e0-171">Click **Network and Internet** and then click **Internet Options**.</span></span>  
  
     <span data-ttu-id="799e0-172">将显示“Internet 选项”对话框。</span><span class="sxs-lookup"><span data-stu-id="799e0-172">The Internet Options dialog box appears.</span></span>  
  
3. <span data-ttu-id="799e0-173">在 **"安全"** 选项卡上，选择要为其配置安全设置的区域。</span><span class="sxs-lookup"><span data-stu-id="799e0-173">On the **Security** tab, select the zone to configure the security settings for.</span></span>  
  
4. <span data-ttu-id="799e0-174">单击 **"自定义级别"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="799e0-174">Click the **Custom Level** button.</span></span>  
  
     <span data-ttu-id="799e0-175">将显示 **"安全设置"** 对话框，您可以配置所选区域的安全设置。</span><span class="sxs-lookup"><span data-stu-id="799e0-175">The **Security Settings** dialog box appears and you can configure the security settings for the selected zone.</span></span>  
  
     ![显示"安全设置"对话框的屏幕截图。](./media/security-wpf/windows-presentation-foundation-security-settings.png)  
  
> [!NOTE]
> <span data-ttu-id="799e0-177">也可以从 Internet Explorer 中进入“Internet 选项”对话框。</span><span class="sxs-lookup"><span data-stu-id="799e0-177">You can also get to the Internet Options dialog box from Internet Explorer.</span></span> <span data-ttu-id="799e0-178">单击**工具**，然后单击**互联网选项**。</span><span class="sxs-lookup"><span data-stu-id="799e0-178">Click **Tools** and then click **Internet Options**.</span></span>  
  
 <span data-ttu-id="799e0-179">从 Windows Internet 资源管理器 7 开始，包括针对 .NET 框架的以下安全设置：</span><span class="sxs-lookup"><span data-stu-id="799e0-179">Starting with Windows Internet Explorer 7, the following security settings specifically for .NET Framework are included:</span></span>  
  
- <span data-ttu-id="799e0-180">**宽松 XAML**。</span><span class="sxs-lookup"><span data-stu-id="799e0-180">**Loose XAML**.</span></span> <span data-ttu-id="799e0-181">控制 Internet 资源管理器是否可以导航到和[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]松散的文件。</span><span class="sxs-lookup"><span data-stu-id="799e0-181">Controls whether Internet Explorer can navigate to and loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] files.</span></span> <span data-ttu-id="799e0-182">（“启用”、“禁用”和“提示”选项）。</span><span class="sxs-lookup"><span data-stu-id="799e0-182">(Enable, Disable, and Prompt options).</span></span>  
  
- <span data-ttu-id="799e0-183">**XAML 浏览器应用程序**。</span><span class="sxs-lookup"><span data-stu-id="799e0-183">**XAML browser applications**.</span></span> <span data-ttu-id="799e0-184">控制 Internet 资源管理器是否可以导航到并运行 XBAP。</span><span class="sxs-lookup"><span data-stu-id="799e0-184">Controls whether Internet Explorer can navigate to and run XBAPs.</span></span> <span data-ttu-id="799e0-185">（“启用”、“禁用”和“提示”选项）。</span><span class="sxs-lookup"><span data-stu-id="799e0-185">(Enable, Disable, and Prompt options).</span></span>  
  
 <span data-ttu-id="799e0-186">默认情况下，这些设置都为**Internet、\*\*\*\*本地 Intranet**和**受信任的站点**区域启用，并且为**受限站点**区域禁用。</span><span class="sxs-lookup"><span data-stu-id="799e0-186">By default, these settings are all enabled for the **Internet**, **Local intranet**, and **Trusted sites** zones, and disabled for the **Restricted sites** zone.</span></span>  
  
<a name="Security_Settings_for_IE6_and_Below"></a>
### <a name="security-related-wpf-registry-settings"></a><span data-ttu-id="799e0-187">与安全相关的 WPF 注册表设置</span><span class="sxs-lookup"><span data-stu-id="799e0-187">Security-related WPF Registry Settings</span></span>  
 <span data-ttu-id="799e0-188">除了可通过“Internet 选项”设置的安全设置之外，还可以通过设置以下注册表值有选择地阻止许多安全敏感 WPF 功能。</span><span class="sxs-lookup"><span data-stu-id="799e0-188">In addition to the security settings available through the Internet Options, the following registry values are available for selectively blocking a number of security-sensitive WPF features.</span></span> <span data-ttu-id="799e0-189">这些值在以下注册表项下定义：</span><span class="sxs-lookup"><span data-stu-id="799e0-189">The values are defined under the following key:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\Windows Presentation Foundation\Features`  
  
 <span data-ttu-id="799e0-190">下表列出了可以设置的值。</span><span class="sxs-lookup"><span data-stu-id="799e0-190">The following table lists the values that can be set.</span></span>  
  
|<span data-ttu-id="799e0-191">值名称</span><span class="sxs-lookup"><span data-stu-id="799e0-191">Value Name</span></span>|<span data-ttu-id="799e0-192">值类型</span><span class="sxs-lookup"><span data-stu-id="799e0-192">Value Type</span></span>|<span data-ttu-id="799e0-193">值数据</span><span class="sxs-lookup"><span data-stu-id="799e0-193">Value Data</span></span>|  
|----------------|----------------|----------------|  
|<span data-ttu-id="799e0-194">XBAPDisallow</span><span class="sxs-lookup"><span data-stu-id="799e0-194">XBAPDisallow</span></span>|<span data-ttu-id="799e0-195">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="799e0-195">REG_DWORD</span></span>|<span data-ttu-id="799e0-196">1 为禁止；0 为允许。</span><span class="sxs-lookup"><span data-stu-id="799e0-196">1 to disallow; 0 to allow.</span></span>|  
|<span data-ttu-id="799e0-197">LooseXamlDisallow</span><span class="sxs-lookup"><span data-stu-id="799e0-197">LooseXamlDisallow</span></span>|<span data-ttu-id="799e0-198">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="799e0-198">REG_DWORD</span></span>|<span data-ttu-id="799e0-199">1 为禁止；0 为允许。</span><span class="sxs-lookup"><span data-stu-id="799e0-199">1 to disallow; 0 to allow.</span></span>|  
|<span data-ttu-id="799e0-200">WebBrowserDisallow</span><span class="sxs-lookup"><span data-stu-id="799e0-200">WebBrowserDisallow</span></span>|<span data-ttu-id="799e0-201">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="799e0-201">REG_DWORD</span></span>|<span data-ttu-id="799e0-202">1 为禁止；0 为允许。</span><span class="sxs-lookup"><span data-stu-id="799e0-202">1 to disallow; 0 to allow.</span></span>|  
|<span data-ttu-id="799e0-203">MediaAudioDisallow</span><span class="sxs-lookup"><span data-stu-id="799e0-203">MediaAudioDisallow</span></span>|<span data-ttu-id="799e0-204">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="799e0-204">REG_DWORD</span></span>|<span data-ttu-id="799e0-205">1 为禁止；0 为允许。</span><span class="sxs-lookup"><span data-stu-id="799e0-205">1 to disallow; 0 to allow.</span></span>|  
|<span data-ttu-id="799e0-206">MediaImageDisallow</span><span class="sxs-lookup"><span data-stu-id="799e0-206">MediaImageDisallow</span></span>|<span data-ttu-id="799e0-207">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="799e0-207">REG_DWORD</span></span>|<span data-ttu-id="799e0-208">1 为禁止；0 为允许。</span><span class="sxs-lookup"><span data-stu-id="799e0-208">1 to disallow; 0 to allow.</span></span>|  
|<span data-ttu-id="799e0-209">MediaVideoDisallow</span><span class="sxs-lookup"><span data-stu-id="799e0-209">MediaVideoDisallow</span></span>|<span data-ttu-id="799e0-210">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="799e0-210">REG_DWORD</span></span>|<span data-ttu-id="799e0-211">1 为禁止；0 为允许。</span><span class="sxs-lookup"><span data-stu-id="799e0-211">1 to disallow; 0 to allow.</span></span>|  
|<span data-ttu-id="799e0-212">ScriptInteropDisallow</span><span class="sxs-lookup"><span data-stu-id="799e0-212">ScriptInteropDisallow</span></span>|<span data-ttu-id="799e0-213">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="799e0-213">REG_DWORD</span></span>|<span data-ttu-id="799e0-214">1 为禁止；0 为允许。</span><span class="sxs-lookup"><span data-stu-id="799e0-214">1 to disallow; 0 to allow.</span></span>|  
  
<a name="webbrowser_control_and_feature_controls"></a>
## <a name="webbrowser-control-and-feature-controls"></a><span data-ttu-id="799e0-215">WebBrowser 控件和功能控件</span><span class="sxs-lookup"><span data-stu-id="799e0-215">WebBrowser Control and Feature Controls</span></span>  
 <span data-ttu-id="799e0-216">WPF<xref:System.Windows.Controls.WebBrowser>控件可用于托管 Web 内容。</span><span class="sxs-lookup"><span data-stu-id="799e0-216">The WPF <xref:System.Windows.Controls.WebBrowser> control can be used to host Web content.</span></span> <span data-ttu-id="799e0-217">WPF<xref:System.Windows.Controls.WebBrowser>控件包装基础 Web 浏览器 ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="799e0-217">The WPF <xref:System.Windows.Controls.WebBrowser> control wraps the underlying WebBrowser ActiveX control.</span></span> <span data-ttu-id="799e0-218">当您使用 WPF<xref:System.Windows.Controls.WebBrowser>控件托管不受信任的 Web 内容时，WPF 为保护应用程序提供了一些支持。</span><span class="sxs-lookup"><span data-stu-id="799e0-218">WPF provides some support for securing your application when you use the WPF <xref:System.Windows.Controls.WebBrowser> control to host untrusted Web content.</span></span> <span data-ttu-id="799e0-219">但是，某些安全功能必须由使用控件<xref:System.Windows.Controls.WebBrowser>的应用程序直接应用。</span><span class="sxs-lookup"><span data-stu-id="799e0-219">However, some security features must be applied directly by the applications using the <xref:System.Windows.Controls.WebBrowser> control.</span></span> <span data-ttu-id="799e0-220">有关 Web 浏览器 ActiveX 控件的详细信息，请参阅[Web 浏览器控件概述和教程](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752041(v=vs.85))。</span><span class="sxs-lookup"><span data-stu-id="799e0-220">For more information about the WebBrowser ActiveX control, see [WebBrowser Control Overviews and Tutorials](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752041(v=vs.85)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="799e0-221">本节也适用于控件，<xref:System.Windows.Controls.Frame>因为它使用<xref:System.Windows.Controls.WebBrowser>导航到 HTML 内容。</span><span class="sxs-lookup"><span data-stu-id="799e0-221">This section also applies to the <xref:System.Windows.Controls.Frame> control since it uses the <xref:System.Windows.Controls.WebBrowser> to navigate to HTML content.</span></span>  
  
 <span data-ttu-id="799e0-222">如果 WPF<xref:System.Windows.Controls.WebBrowser>控件用于托管不受信任的 Web 内容，则应用程序应使用部分信任<xref:System.AppDomain>来帮助将应用程序代码与潜在的恶意 HTML 脚本代码隔离。</span><span class="sxs-lookup"><span data-stu-id="799e0-222">If the WPF <xref:System.Windows.Controls.WebBrowser> control is used to host untrusted Web content, your application should use a partial-trust <xref:System.AppDomain> to help insulate your application code from potentially malicious HTML script code.</span></span> <span data-ttu-id="799e0-223">如果应用程序使用<xref:System.Windows.Controls.WebBrowser.InvokeScript%2A>方法和<xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A>属性与托管脚本交互，则尤其如此。</span><span class="sxs-lookup"><span data-stu-id="799e0-223">This is especially true if your application is interacting with the hosted script by using the <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A> method and the <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A> property.</span></span> <span data-ttu-id="799e0-224">有关详细信息，请参阅[WPF 加载项概述](./app-development/wpf-add-ins-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="799e0-224">For more information, see [WPF Add-Ins Overview](./app-development/wpf-add-ins-overview.md).</span></span>  
  
 <span data-ttu-id="799e0-225">如果应用程序使用 WPF<xref:System.Windows.Controls.WebBrowser>控件，则提高安全性和缓解攻击的另一种方法是启用 Internet Explorer 功能控件。</span><span class="sxs-lookup"><span data-stu-id="799e0-225">If your application uses the WPF <xref:System.Windows.Controls.WebBrowser> control, another way to increase security and mitigate attacks is to enable Internet Explorer feature controls.</span></span> <span data-ttu-id="799e0-226">功能控件是 Internet 资源管理器的补充，允许管理员和开发人员配置 Internet Explorer 的功能以及承载 WebBrowser ActiveX 控件的应用程序，WPF<xref:System.Windows.Controls.WebBrowser>控件将该控件包装。</span><span class="sxs-lookup"><span data-stu-id="799e0-226">Feature controls are additions to Internet Explorer that allow administrators and developers to configure features of Internet Explorer and applications that host the WebBrowser ActiveX control, which the WPF <xref:System.Windows.Controls.WebBrowser> control wraps.</span></span> <span data-ttu-id="799e0-227">可以使用[CoInternetSetFeature 启用功能](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537168(v=vs.85))或更改注册表中的值来配置功能控件。</span><span class="sxs-lookup"><span data-stu-id="799e0-227">Feature controls can be configured by using the [CoInternetSetFeatureEnabled](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537168(v=vs.85)) function or by changing values in the registry.</span></span> <span data-ttu-id="799e0-228">有关功能控件的详细信息，请参阅[功能控制和](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537184(v=vs.85)) [Internet 功能控件](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/general-info/ee330720(v=vs.85))简介。</span><span class="sxs-lookup"><span data-stu-id="799e0-228">For more information about feature controls, see [Introduction to Feature Controls](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537184(v=vs.85)) and [Internet Feature Controls](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/general-info/ee330720(v=vs.85)).</span></span>  
  
 <span data-ttu-id="799e0-229">如果您正在开发使用 WPF 控件的独立 WPF<xref:System.Windows.Controls.WebBrowser>应用程序，WPF 会自动为应用程序启用以下功能控件。</span><span class="sxs-lookup"><span data-stu-id="799e0-229">If you are developing a standalone WPF application that uses the WPF <xref:System.Windows.Controls.WebBrowser> control, WPF automatically enables the following feature controls for your application.</span></span>  
  
|<span data-ttu-id="799e0-230">功能控件</span><span class="sxs-lookup"><span data-stu-id="799e0-230">Feature Control</span></span>|  
|---------------------|  
|<span data-ttu-id="799e0-231">FEATURE_MIME_HANDLING</span><span class="sxs-lookup"><span data-stu-id="799e0-231">FEATURE_MIME_HANDLING</span></span>|  
|<span data-ttu-id="799e0-232">FEATURE_MIME_SNIFFING</span><span class="sxs-lookup"><span data-stu-id="799e0-232">FEATURE_MIME_SNIFFING</span></span>|  
|<span data-ttu-id="799e0-233">FEATURE_OBJECT_CACHING</span><span class="sxs-lookup"><span data-stu-id="799e0-233">FEATURE_OBJECT_CACHING</span></span>|  
|<span data-ttu-id="799e0-234">FEATURE_SAFE_BINDTOOBJECT</span><span class="sxs-lookup"><span data-stu-id="799e0-234">FEATURE_SAFE_BINDTOOBJECT</span></span>|  
|<span data-ttu-id="799e0-235">FEATURE_WINDOW_RESTRICTIONS</span><span class="sxs-lookup"><span data-stu-id="799e0-235">FEATURE_WINDOW_RESTRICTIONS</span></span>|  
|<span data-ttu-id="799e0-236">FEATURE_ZONE_ELEVATION</span><span class="sxs-lookup"><span data-stu-id="799e0-236">FEATURE_ZONE_ELEVATION</span></span>|  
|<span data-ttu-id="799e0-237">FEATURE_RESTRICT_FILEDOWNLOAD</span><span class="sxs-lookup"><span data-stu-id="799e0-237">FEATURE_RESTRICT_FILEDOWNLOAD</span></span>|  
|<span data-ttu-id="799e0-238">FEATURE_RESTRICT_ACTIVEXINSTALL</span><span class="sxs-lookup"><span data-stu-id="799e0-238">FEATURE_RESTRICT_ACTIVEXINSTALL</span></span>|  
|<span data-ttu-id="799e0-239">FEATURE_ADDON_MANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="799e0-239">FEATURE_ADDON_MANAGEMENT</span></span>|  
|<span data-ttu-id="799e0-240">FEATURE_HTTP_USERNAME_PASSWORD_DISABLE</span><span class="sxs-lookup"><span data-stu-id="799e0-240">FEATURE_HTTP_USERNAME_PASSWORD_DISABLE</span></span>|  
|<span data-ttu-id="799e0-241">FEATURE_SECURITYBAND</span><span class="sxs-lookup"><span data-stu-id="799e0-241">FEATURE_SECURITYBAND</span></span>|  
|<span data-ttu-id="799e0-242">FEATURE_UNC_SAVEDFILECHECK</span><span class="sxs-lookup"><span data-stu-id="799e0-242">FEATURE_UNC_SAVEDFILECHECK</span></span>|  
|<span data-ttu-id="799e0-243">FEATURE_VALIDATE_NAVIGATE_URL</span><span class="sxs-lookup"><span data-stu-id="799e0-243">FEATURE_VALIDATE_NAVIGATE_URL</span></span>|  
|<span data-ttu-id="799e0-244">FEATURE_DISABLE_TELNET_PROTOCOL</span><span class="sxs-lookup"><span data-stu-id="799e0-244">FEATURE_DISABLE_TELNET_PROTOCOL</span></span>|  
|<span data-ttu-id="799e0-245">FEATURE_WEBOC_POPUPMANAGEMENT</span><span class="sxs-lookup"><span data-stu-id="799e0-245">FEATURE_WEBOC_POPUPMANAGEMENT</span></span>|  
|<span data-ttu-id="799e0-246">FEATURE_DISABLE_LEGACY_COMPRESSION</span><span class="sxs-lookup"><span data-stu-id="799e0-246">FEATURE_DISABLE_LEGACY_COMPRESSION</span></span>|  
|<span data-ttu-id="799e0-247">FEATURE_SSLUX</span><span class="sxs-lookup"><span data-stu-id="799e0-247">FEATURE_SSLUX</span></span>|  
  
 <span data-ttu-id="799e0-248">由于这些功能控件是无条件启用的，因此它们可能会对完全信任的应用程序造成损害。</span><span class="sxs-lookup"><span data-stu-id="799e0-248">Since these feature controls are enabled unconditionally, a full-trust application might be impaired by them.</span></span> <span data-ttu-id="799e0-249">在这种情况下，如果特定应用程序及其承载的内容没有安全风险，则可以禁用相应的功能控件。</span><span class="sxs-lookup"><span data-stu-id="799e0-249">In this case, if there is no security risk for the specific application and the content it is hosting, the corresponding feature control can be disabled.</span></span>  
  
 <span data-ttu-id="799e0-250">功能控件由实例化 Web 浏览器 ActiveX 对象的过程应用。</span><span class="sxs-lookup"><span data-stu-id="799e0-250">Feature controls are applied by the process instantiating the WebBrowser ActiveX object.</span></span> <span data-ttu-id="799e0-251">因此，如果要创建可导航到不受信任的内容的独立应用程序，则应该认真考虑启用附加功能控件。</span><span class="sxs-lookup"><span data-stu-id="799e0-251">Therefore, if you are creating a stand-alone application that can navigate to untrusted content, you should seriously consider enabling additional feature controls.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="799e0-252">此建议是根据 MSHTML 和 SHDOCVW 主机安全性的一般性建议提出的。</span><span class="sxs-lookup"><span data-stu-id="799e0-252">This recommendation is based on general recommendations for MSHTML and SHDOCVW host security.</span></span> <span data-ttu-id="799e0-253">有关详细信息，请参阅[MSHTML 主机安全常见问题解答：II 部分 I](https://msrc-blog.microsoft.com/2009/04/02/the-mshtml-host-security-faq-part-i-of-ii/)和[MSHTML 主机安全常见问题解答：II 的第二部分](https://msrc-blog.microsoft.com/2009/04/03/the-mshtml-host-security-faq-part-ii-of-ii/)。</span><span class="sxs-lookup"><span data-stu-id="799e0-253">For more information, see [The MSHTML Host Security FAQ: Part I of II](https://msrc-blog.microsoft.com/2009/04/02/the-mshtml-host-security-faq-part-i-of-ii/) and [The MSHTML Host Security FAQ: Part II of II](https://msrc-blog.microsoft.com/2009/04/03/the-mshtml-host-security-faq-part-ii-of-ii/).</span></span>  
  
 <span data-ttu-id="799e0-254">对于可执行文件，请考虑通过将注册表值设置为 1 来启用以下功能控件。</span><span class="sxs-lookup"><span data-stu-id="799e0-254">For your executable, consider enabling the following feature controls by setting the registry value to 1.</span></span>  
  
|<span data-ttu-id="799e0-255">功能控件</span><span class="sxs-lookup"><span data-stu-id="799e0-255">Feature Control</span></span>|  
|---------------------|  
|<span data-ttu-id="799e0-256">FEATURE_ACTIVEX_REPURPOSEDETECTION</span><span class="sxs-lookup"><span data-stu-id="799e0-256">FEATURE_ACTIVEX_REPURPOSEDETECTION</span></span>|  
|<span data-ttu-id="799e0-257">FEATURE_BLOCK_LMZ_IMG</span><span class="sxs-lookup"><span data-stu-id="799e0-257">FEATURE_BLOCK_LMZ_IMG</span></span>|  
|<span data-ttu-id="799e0-258">FEATURE_BLOCK_LMZ_OBJECT</span><span class="sxs-lookup"><span data-stu-id="799e0-258">FEATURE_BLOCK_LMZ_OBJECT</span></span>|  
|<span data-ttu-id="799e0-259">FEATURE_BLOCK_LMZ_SCRIPT</span><span class="sxs-lookup"><span data-stu-id="799e0-259">FEATURE_BLOCK_LMZ_SCRIPT</span></span>|  
|<span data-ttu-id="799e0-260">FEATURE_RESTRICT_RES_TO_LMZ</span><span class="sxs-lookup"><span data-stu-id="799e0-260">FEATURE_RESTRICT_RES_TO_LMZ</span></span>|  
|<span data-ttu-id="799e0-261">FEATURE_RESTRICT_ABOUT_PROTOCOL_IE7</span><span class="sxs-lookup"><span data-stu-id="799e0-261">FEATURE_RESTRICT_ABOUT_PROTOCOL_IE7</span></span>|  
|<span data-ttu-id="799e0-262">FEATURE_SHOW_APP_PROTOCOL_WARN_DIALOG</span><span class="sxs-lookup"><span data-stu-id="799e0-262">FEATURE_SHOW_APP_PROTOCOL_WARN_DIALOG</span></span>|  
|<span data-ttu-id="799e0-263">FEATURE_LOCALMACHINE_LOCKDOWN</span><span class="sxs-lookup"><span data-stu-id="799e0-263">FEATURE_LOCALMACHINE_LOCKDOWN</span></span>|  
|<span data-ttu-id="799e0-264">FEATURE_FORCE_ADDR_AND_STATUS</span><span class="sxs-lookup"><span data-stu-id="799e0-264">FEATURE_FORCE_ADDR_AND_STATUS</span></span>|  
|<span data-ttu-id="799e0-265">FEATURE_RESTRICTED_ZONE_WHEN_FILE_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="799e0-265">FEATURE_RESTRICTED_ZONE_WHEN_FILE_NOT_FOUND</span></span>|  
  
 <span data-ttu-id="799e0-266">对于可执行文件，请考虑通过将注册表值设置为 0 来禁用以下功能控件。</span><span class="sxs-lookup"><span data-stu-id="799e0-266">For your executable, consider disabling the following feature control by setting the registry value to 0.</span></span>  
  
|<span data-ttu-id="799e0-267">功能控件</span><span class="sxs-lookup"><span data-stu-id="799e0-267">Feature Control</span></span>|  
|---------------------|  
|<span data-ttu-id="799e0-268">FEATURE_ENABLE_SCRIPT_PASTE_URLACTION_IF_PROMPT</span><span class="sxs-lookup"><span data-stu-id="799e0-268">FEATURE_ENABLE_SCRIPT_PASTE_URLACTION_IF_PROMPT</span></span>|  
  
 <span data-ttu-id="799e0-269">如果运行部分信任的 XAML 浏览器应用程序 （XBAP），该应用程序在<xref:System.Windows.Controls.WebBrowser>Windows Internet 资源管理器中包含 WPF 控件，则 WPF 在 Internet 资源管理器进程的地址空间中托管 Web 浏览器 ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="799e0-269">If you run a partial-trust XAML browser application (XBAP) that includes a WPF <xref:System.Windows.Controls.WebBrowser> control in Windows Internet Explorer, WPF hosts the WebBrowser ActiveX control in the address space of the Internet Explorer process.</span></span> <span data-ttu-id="799e0-270">由于 Web 浏览器 ActiveX 控件托管在 Internet 资源管理器过程中，因此 Internet Explorer 的所有功能控件也已为 Web 浏览器 ActiveX 控件启用。</span><span class="sxs-lookup"><span data-stu-id="799e0-270">Since the WebBrowser ActiveX control is hosted in the Internet Explorer process, all of the feature controls for Internet Explorer are also enabled for the WebBrowser ActiveX control.</span></span>  
  
 <span data-ttu-id="799e0-271">与普通的独立应用程序相比，运行于 Internet Explorer 中的 XBAP 还将另外获得一层安全保护。</span><span class="sxs-lookup"><span data-stu-id="799e0-271">XBAPs running in Internet Explorer also get an additional level of security compared to normal standalone applications.</span></span> <span data-ttu-id="799e0-272">这种额外的安全性是因为 Internet 资源管理器（因此是 Web 浏览器 ActiveX 控件）默认在 Windows Vista 和 Windows 7 上以受保护模式运行。</span><span class="sxs-lookup"><span data-stu-id="799e0-272">This additional security is because Internet Explorer, and therefore the WebBrowser ActiveX control, runs in protected mode by default on Windows Vista and Windows 7.</span></span> <span data-ttu-id="799e0-273">有关受保护模式的详细信息，请参阅[在受保护模式下了解和工作 Internet 资源管理器](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/)。</span><span class="sxs-lookup"><span data-stu-id="799e0-273">For more information about protected mode, see [Understanding and Working in Protected Mode Internet Explorer](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="799e0-274">如果您尝试运行一个 XBAP，该 XBAP 在 Firefox 中包含<xref:System.Windows.Controls.WebBrowser>WPF<xref:System.Security.SecurityException>控件，而在 Internet 区域中，将引发 。</span><span class="sxs-lookup"><span data-stu-id="799e0-274">If you try to run an XBAP that includes a WPF <xref:System.Windows.Controls.WebBrowser> control in Firefox, while in the Internet zone, a <xref:System.Security.SecurityException> will be thrown.</span></span> <span data-ttu-id="799e0-275">这是由于 WPF 安全策略造成的。</span><span class="sxs-lookup"><span data-stu-id="799e0-275">This is due to WPF security policy.</span></span>  
  
<a name="APTCA"></a>
## <a name="disabling-aptca-assemblies-for-partially-trusted-client-applications"></a><span data-ttu-id="799e0-276">对部分受信任的客户端应用程序禁用 APTCA 程序集</span><span class="sxs-lookup"><span data-stu-id="799e0-276">Disabling APTCA Assemblies for Partially Trusted Client Applications</span></span>  
 <span data-ttu-id="799e0-277">当托管程序集安装到全局程序集缓存 （GAC） 中时，它们将完全受信任，因为用户必须提供显式权限才能安装它们。</span><span class="sxs-lookup"><span data-stu-id="799e0-277">When managed assemblies are installed into the global assembly cache (GAC), they become fully trusted because the user must provide explicit permission to install them.</span></span> <span data-ttu-id="799e0-278">因为这些程序集是完全受信任的，所以只有完全受信任的托管客户端应用程序才可以使用它们。</span><span class="sxs-lookup"><span data-stu-id="799e0-278">Because they are fully trusted, only fully trusted managed client applications can use them.</span></span> <span data-ttu-id="799e0-279">要允许部分受信任的应用程序使用它们，必须用<xref:System.Security.AllowPartiallyTrustedCallersAttribute>（APTCA） 标记它们。</span><span class="sxs-lookup"><span data-stu-id="799e0-279">To allow partially trusted applications to use them, they must be marked with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA).</span></span> <span data-ttu-id="799e0-280">仅当程序集经过测试，可在部分信任的情况下安全执行时，才应该为其标记此特性。</span><span class="sxs-lookup"><span data-stu-id="799e0-280">Only assemblies that have been tested to be safe for execution in partial trust should be marked with this attribute.</span></span>  
  
 <span data-ttu-id="799e0-281">但是，APTCA 程序集在安装到 GAC 后可能会表现出安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="799e0-281">However, it is possible for an APTCA assembly to exhibit a security flaw after being installed into the  GAC .</span></span> <span data-ttu-id="799e0-282">一旦发现安全漏洞，程序集发布者可以生成安全更新来修复现有安装上的问题，还可以阻止问题发现后进行的安装操作。</span><span class="sxs-lookup"><span data-stu-id="799e0-282">Once a security flaw is discovered, assembly publishers can produce a security update to fix the problem on existing installations, and to protect against installations that may occur after the problem is discovered.</span></span> <span data-ttu-id="799e0-283">其中一个更新选项是卸载程序集，即使这可能中断使用该程序集的其他完全受信任的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="799e0-283">One option for the update is to uninstall the assembly, although that may break other fully trusted client applications that use the assembly.</span></span>  
  
 <span data-ttu-id="799e0-284">WPF 提供了一种机制，通过该机制，无需卸载 APTCA 程序集，即可禁用 APTCA 程序集，以用于部分受信任的 XBAPs。</span><span class="sxs-lookup"><span data-stu-id="799e0-284">WPF provides a mechanism by which an APTCA assembly can be disabled for partially trusted XBAPs without uninstalling the APTCA assembly.</span></span>  
  
 <span data-ttu-id="799e0-285">若要禁用 APTCA 程序集，必须创建一个特殊的注册表项：</span><span class="sxs-lookup"><span data-stu-id="799e0-285">To disable an APTCA assembly, you have to create a special registry key:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 <span data-ttu-id="799e0-286">示例如下：</span><span class="sxs-lookup"><span data-stu-id="799e0-286">The following shows an example:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 <span data-ttu-id="799e0-287">此项建立 APTCA 程序集的条目。</span><span class="sxs-lookup"><span data-stu-id="799e0-287">This key establishes an entry for the APTCA assembly.</span></span> <span data-ttu-id="799e0-288">还必须在此项中创建值来启用或禁用程序集。</span><span class="sxs-lookup"><span data-stu-id="799e0-288">You also have to create a value in this key that enables or disables the assembly.</span></span> <span data-ttu-id="799e0-289">下面是该值的详细信息：</span><span class="sxs-lookup"><span data-stu-id="799e0-289">The following are the details of the value:</span></span>  
  
- <span data-ttu-id="799e0-290">值名称 **：APTCA_FLAG**。</span><span class="sxs-lookup"><span data-stu-id="799e0-290">Value Name: **APTCA_FLAG**.</span></span>  
  
- <span data-ttu-id="799e0-291">值类型 **：REG_DWORD**。</span><span class="sxs-lookup"><span data-stu-id="799e0-291">Value Type: **REG_DWORD**.</span></span>  
  
- <span data-ttu-id="799e0-292">值数据 **：1**个要禁用;**0**启用。</span><span class="sxs-lookup"><span data-stu-id="799e0-292">Value Data: **1** to disable; **0** to enable.</span></span>  
  
 <span data-ttu-id="799e0-293">如果必须为部分受信任的客户端应用程序禁用某程序集，可以编写一个用于创建注册表项和值的更新。</span><span class="sxs-lookup"><span data-stu-id="799e0-293">If an assembly has to be disabled for partially trusted client applications, you can write an update that creates the registry key and value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="799e0-294">Core .NET 框架程序集不会以这种方式禁用它们，因为它们是托管应用程序运行所必需的。</span><span class="sxs-lookup"><span data-stu-id="799e0-294">Core .NET Framework assemblies are not affected by disabling them in this way because they are required for managed applications to run.</span></span> <span data-ttu-id="799e0-295">对禁用 APTCA 程序集的支持主要面向第三方应用程序。</span><span class="sxs-lookup"><span data-stu-id="799e0-295">Support for disabling APTCA assemblies is primarily targeted to third-party applications.</span></span>  
  
<a name="LooseContentSandboxing"></a>
## <a name="sandbox-behavior-for-loose-xaml-files"></a><span data-ttu-id="799e0-296">宽松 XAML 文件的沙盒行为</span><span class="sxs-lookup"><span data-stu-id="799e0-296">Sandbox Behavior for Loose XAML Files</span></span>  
 <span data-ttu-id="799e0-297">松散[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]文件是仅标记的 XAML 文件，不依赖于任何代码备份、事件处理程序或特定于应用程序的程序集。</span><span class="sxs-lookup"><span data-stu-id="799e0-297">Loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] files are markup-only XAML files that do not depend on any code-behind, event handler, or application-specific assembly.</span></span> <span data-ttu-id="799e0-298">当松散[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]文件直接从浏览器导航到时，它们将基于默认 Internet 区域权限集加载到安全沙盒中。</span><span class="sxs-lookup"><span data-stu-id="799e0-298">When loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] files are navigated to directly from the browser, they are loaded in a security sandbox based on the default Internet zone permission set.</span></span>  
  
 <span data-ttu-id="799e0-299">但是，当松散[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]文件从 或<xref:System.Windows.Navigation.NavigationWindow>在独立应用程序中导航到时<xref:System.Windows.Controls.Frame>，安全行为会有所不同。</span><span class="sxs-lookup"><span data-stu-id="799e0-299">However, the security behavior is different when loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] files are navigated to from either a <xref:System.Windows.Navigation.NavigationWindow> or <xref:System.Windows.Controls.Frame> in a standalone application.</span></span>  
  
 <span data-ttu-id="799e0-300">在这两种情况下，导航以[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]继承其主机应用程序权限的松散文件。</span><span class="sxs-lookup"><span data-stu-id="799e0-300">In both cases, the loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file that is navigated to inherits the permissions of its host application.</span></span> <span data-ttu-id="799e0-301">但是，从安全角度来看，此行为可能是不可取的，尤其是在由不[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]受信任的实体或未知实体生成的松散文件的情况下。</span><span class="sxs-lookup"><span data-stu-id="799e0-301">However, this behavior may be undesirable from a security perspective, particularly if a loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file was produced by an entity that is either not trusted or unknown.</span></span> <span data-ttu-id="799e0-302">这种类型的内容称为*外部内容*，<xref:System.Windows.Controls.Frame>并且<xref:System.Windows.Navigation.NavigationWindow>可以配置为在导航到时将其隔离。</span><span class="sxs-lookup"><span data-stu-id="799e0-302">This type of content is known as *external content*, and both <xref:System.Windows.Controls.Frame> and <xref:System.Windows.Navigation.NavigationWindow> can be configured to isolate it when navigated to.</span></span> <span data-ttu-id="799e0-303">通过将**沙盒外部内容**属性设置为 true 来实现隔离，如 以下示例<xref:System.Windows.Controls.Frame>所示， <xref:System.Windows.Navigation.NavigationWindow></span><span class="sxs-lookup"><span data-stu-id="799e0-303">Isolation is achieved by setting the **SandboxExternalContent** property to true, as shown in the following examples for <xref:System.Windows.Controls.Frame> and <xref:System.Windows.Navigation.NavigationWindow>:</span></span>  
  
 [!code-xaml[SecurityOverviewSnippets#FrameMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xaml[SecurityOverviewSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 <span data-ttu-id="799e0-304">使用此设置，外部内容将加载到不同于承载应用程序的进程的进程中。</span><span class="sxs-lookup"><span data-stu-id="799e0-304">With this setting, external content will be loaded into a process that is separate from the process that is hosting the application.</span></span> <span data-ttu-id="799e0-305">此进程被限制在默认 Internet 区域权限集中，从而有效地将其与承载应用程序和客户端计算机隔离。</span><span class="sxs-lookup"><span data-stu-id="799e0-305">This process is restricted to the default Internet zone permission set, effectively isolating it from the hosting application and the client computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="799e0-306">即使基于 WPF[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]浏览器托管基础结构<xref:System.Windows.Navigation.NavigationWindow>（<xref:System.Windows.Controls.Frame>涉及演示文稿主机进程）实现从 a 或独立应用程序中对松散文件的导航，安全级别比直接在 Windows Vista 和 Windows 7 上的 Internet 资源管理器中加载的内容（这仍通过演示主机）时略低。</span><span class="sxs-lookup"><span data-stu-id="799e0-306">Even though navigation to loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] files from either a <xref:System.Windows.Navigation.NavigationWindow> or <xref:System.Windows.Controls.Frame> in a standalone application is implemented based on the WPF browser hosting infrastructure, involving the PresentationHost process, the security level is slightly less than when the content is loaded directly in Internet Explorer on Windows Vista and Windows 7 (which would still be through PresentationHost).</span></span> <span data-ttu-id="799e0-307">这是因为使用 Web 浏览器的独立 WPF 应用程序不提供 Internet Explorer 的额外“保护模式”安全功能。</span><span class="sxs-lookup"><span data-stu-id="799e0-307">This is because a standalone WPF application using a Web browser does not provide the additional Protected Mode security feature of Internet Explorer.</span></span>  
  
<a name="BestPractices"></a>
## <a name="resources-for-developing-wpf-applications-that-promote-security"></a><span data-ttu-id="799e0-308">用于开发可提高安全性的 WPF 应用程序的资源</span><span class="sxs-lookup"><span data-stu-id="799e0-308">Resources for Developing WPF Applications that Promote Security</span></span>  
 <span data-ttu-id="799e0-309">以下是一些其他资源，可帮助开发 WPF 应用程序，以提高安全性：</span><span class="sxs-lookup"><span data-stu-id="799e0-309">The following are some additional resources to help develop WPF applications that promote security:</span></span>  
  
|<span data-ttu-id="799e0-310">区域</span><span class="sxs-lookup"><span data-stu-id="799e0-310">Area</span></span>|<span data-ttu-id="799e0-311">资源</span><span class="sxs-lookup"><span data-stu-id="799e0-311">Resource</span></span>|  
|----------|--------------|  
|<span data-ttu-id="799e0-312">托管代码</span><span class="sxs-lookup"><span data-stu-id="799e0-312">Managed code</span></span>|<span data-ttu-id="799e0-313">[应用程序的模式和实践安全指南](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="799e0-313">[Patterns and Practices Security Guidance for Applications](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span></span>|  
|<span data-ttu-id="799e0-314">CAS</span><span class="sxs-lookup"><span data-stu-id="799e0-314">CAS</span></span>|[<span data-ttu-id="799e0-315">代码访问安全性</span><span class="sxs-lookup"><span data-stu-id="799e0-315">Code Access Security</span></span>](../misc/code-access-security.md)|  
|<span data-ttu-id="799e0-316">ClickOnce</span><span class="sxs-lookup"><span data-stu-id="799e0-316">ClickOnce</span></span>|[<span data-ttu-id="799e0-317">ClickOnce 安全和部署</span><span class="sxs-lookup"><span data-stu-id="799e0-317">ClickOnce Security and Deployment</span></span>](/visualstudio/deployment/clickonce-security-and-deployment)|  
|<span data-ttu-id="799e0-318">WPF</span><span class="sxs-lookup"><span data-stu-id="799e0-318">WPF</span></span>|[<span data-ttu-id="799e0-319">WPF 部分信任安全</span><span class="sxs-lookup"><span data-stu-id="799e0-319">WPF Partial Trust Security</span></span>](wpf-partial-trust-security.md)|  
  
## <a name="see-also"></a><span data-ttu-id="799e0-320">另请参阅</span><span class="sxs-lookup"><span data-stu-id="799e0-320">See also</span></span>

- [<span data-ttu-id="799e0-321">WPF 部分信任安全</span><span class="sxs-lookup"><span data-stu-id="799e0-321">WPF Partial Trust Security</span></span>](wpf-partial-trust-security.md)
- [<span data-ttu-id="799e0-322">WPF 安全策略 - 平台安全性</span><span class="sxs-lookup"><span data-stu-id="799e0-322">WPF Security Strategy - Platform Security</span></span>](wpf-security-strategy-platform-security.md)
- [<span data-ttu-id="799e0-323">WPF 安全策略 - 安全工程</span><span class="sxs-lookup"><span data-stu-id="799e0-323">WPF Security Strategy - Security Engineering</span></span>](wpf-security-strategy-security-engineering.md)
- <span data-ttu-id="799e0-324">[应用程序的模式和实践安全指南](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="799e0-324">[Patterns and Practices Security Guidance for Applications](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span></span>
- [<span data-ttu-id="799e0-325">代码访问安全性</span><span class="sxs-lookup"><span data-stu-id="799e0-325">Code Access Security</span></span>](../misc/code-access-security.md)
- [<span data-ttu-id="799e0-326">ClickOnce 安全和部署</span><span class="sxs-lookup"><span data-stu-id="799e0-326">ClickOnce Security and Deployment</span></span>](/visualstudio/deployment/clickonce-security-and-deployment)
- [<span data-ttu-id="799e0-327">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="799e0-327">XAML Overview (WPF)</span></span>](../../desktop-wpf/fundamentals/xaml.md)
