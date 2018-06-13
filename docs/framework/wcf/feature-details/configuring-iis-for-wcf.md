---
title: 为 Windows Communication Foundation 配置 Internet Information Services 7.0
ms.date: 03/30/2017
ms.assetid: 1050d395-092e-44d3-b4ba-66be3b039ffb
ms.openlocfilehash: 3e34f46fbf3ccf12c6a89a7cac96143965d958d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491711"
---
# <a name="configuring-internet-information-services-70-for-windows-communication-foundation"></a><span data-ttu-id="5fcf6-102">为 Windows Communication Foundation 配置 Internet Information Services 7.0</span><span class="sxs-lookup"><span data-stu-id="5fcf6-102">Configuring Internet Information Services 7.0 for Windows Communication Foundation</span></span>
<span data-ttu-id="5fcf6-103">Internet Information Services (IIS) 7.0 具有模块化设计，允许有选择地安装需要的组件。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-103">Internet Information Services (IIS) 7.0 has a modular design that allows you to selectively install components that are required.</span></span> <span data-ttu-id="5fcf6-104">此设计基于在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 中引入的新清单驱动的组件化技术。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-104">This design is based on the new manifest-driven componentization technology introduced in [!INCLUDE[wv](../../../../includes/wv-md.md)].</span></span> <span data-ttu-id="5fcf6-105">[!INCLUDE[iisver](../../../../includes/iisver-md.md)] 有 40 多个独立功能组件可以独立安装。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-105">There are more than 40 standalone feature components of [!INCLUDE[iisver](../../../../includes/iisver-md.md)] that can be installed independently.</span></span> <span data-ttu-id="5fcf6-106">这使 IT 专业人士能够轻松地按需要自定义安装。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-106">This allows IT professionals to easily customize the installation as required.</span></span> <span data-ttu-id="5fcf6-107">本主题讨论如何配置[!INCLUDE[iisver](../../../../includes/iisver-md.md)]有关使用 Windows Communication Foundation (WCF) 并确定所需的组件。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-107">This topic discusses how to configure [!INCLUDE[iisver](../../../../includes/iisver-md.md)] for use with Windows Communication Foundation (WCF) and determine which components are required.</span></span>  
  
## <a name="minimal-installation-installing-was"></a><span data-ttu-id="5fcf6-108">最小安装：安装 WAS</span><span class="sxs-lookup"><span data-stu-id="5fcf6-108">Minimal Installation: Installing WAS</span></span>  
 <span data-ttu-id="5fcf6-109">整个 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 软件包的最小安装是安装 Windows Process Activation Service (WAS)。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-109">The minimal installation of the whole [!INCLUDE[iisver](../../../../includes/iisver-md.md)] package is to install the Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="5fcf6-110">WAS 是一种独立的功能，是 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 中唯一可用于所有 [!INCLUDE[wv](../../../../includes/wv-md.md)] 操作系统（Home Basic、Home Premium、Business 以及 Ultimate 和 Enterprise）的功能。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-110">WAS is a standalone feature and it is the only feature from the [!INCLUDE[iisver](../../../../includes/iisver-md.md)] that is available for all [!INCLUDE[wv](../../../../includes/wv-md.md)] operating systems (Home Basic, Home Premium, Business, and Ultimate and Enterprise).</span></span>  
  
 <span data-ttu-id="5fcf6-111">从控制面板中，单击**程序**，然后单击**打开或关闭 Windows 功能**下面列出**程序和功能**，WAS 组件显示在如下图所示的列表。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-111">From the Control Panel, click **Programs** and then click **Turn Windows features on or off** which is listed under **Programs and Features**, the WAS component is shown in the list as in the following illustration.</span></span>  
  
 <span data-ttu-id="5fcf6-112">![打开功能或关闭对话框](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")</span><span class="sxs-lookup"><span data-stu-id="5fcf6-112">![Turn Features On or Off Dialog](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")</span></span>  
  
 <span data-ttu-id="5fcf6-113">此功能具有下列子组件：</span><span class="sxs-lookup"><span data-stu-id="5fcf6-113">This feature has the following sub-components:</span></span>  
  
-   <span data-ttu-id="5fcf6-114">.NET Environment</span><span class="sxs-lookup"><span data-stu-id="5fcf6-114">.NET Environment</span></span>  
  
-   <span data-ttu-id="5fcf6-115">配置 API</span><span class="sxs-lookup"><span data-stu-id="5fcf6-115">Configuration APIs</span></span>  
  
-   <span data-ttu-id="5fcf6-116">进程模型</span><span class="sxs-lookup"><span data-stu-id="5fcf6-116">Process Model</span></span>  
  
 <span data-ttu-id="5fcf6-117">如果选择 WAS 的根节点仅**进程模型**默认选中子节点。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-117">If you select the root node of WAS, only the **Process Model** sub-node is checked by default.</span></span> <span data-ttu-id="5fcf6-118">请注意，使用此安装时，你将只安装 WAS，因为没有用于 Web 服务器的支持功能。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-118">Please note that with this installation you are only installing WAS, because there is no support for a Web server.</span></span>  
  
 <span data-ttu-id="5fcf6-119">若要使 WCF 或任何[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]应用程序，以检查 **.NET 环境**复选框。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-119">To make WCF or any [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application to work, check the **.NET Environment** checkbox.</span></span> <span data-ttu-id="5fcf6-120">这意味着所有 WAS 组件所需使 WCF 和[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]正常工作。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-120">This means that all of WAS components are required to make WCF and [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] to work well.</span></span> <span data-ttu-id="5fcf6-121">您安装其中任何组件后，会自动选中这些组件。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-121">These are automatically checked once you install any of those components.</span></span>  
  
## <a name="iis-70-default-installation"></a><span data-ttu-id="5fcf6-122">IIS 7.0：默认安装</span><span class="sxs-lookup"><span data-stu-id="5fcf6-122">IIS 7.0: Default Installation</span></span>  
 <span data-ttu-id="5fcf6-123">通过检查**Internet Information Services**功能，某些子节点会自动选中下面的插图中所示。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-123">By checking the **Internet Information Services** feature, some of the sub-nodes are automatically checked as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="5fcf6-124">![IIS 7.0 功能的默认设置](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")</span><span class="sxs-lookup"><span data-stu-id="5fcf6-124">![Default settings for IIS 7.0 features](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")</span></span>  
  
 <span data-ttu-id="5fcf6-125">这是 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 的默认安装。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-125">This is the default installation of [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span></span> <span data-ttu-id="5fcf6-126">使用此安装时，您可以使用 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 提供静态内容（如 HTML 页面和其他内容）。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-126">With this installation, you can use [!INCLUDE[iisver](../../../../includes/iisver-md.md)] to service static content (such as HTML pages and other content).</span></span> <span data-ttu-id="5fcf6-127">但是，无法运行[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]或 CGI 应用程序或托管 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-127">However, you cannot run [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] or CGI applications or host WCF services.</span></span>  
  
## <a name="iis-70-installation-with-aspnet-support"></a><span data-ttu-id="5fcf6-128">IIS 7.0：带 ASP.NET 支持的安装</span><span class="sxs-lookup"><span data-stu-id="5fcf6-128">IIS 7.0: Installation with ASP.NET Support</span></span>  
 <span data-ttu-id="5fcf6-129">您必须安装 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 才能使 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 在 IIS 7.0 上正常工作。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-129">You must install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] to make [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] work on IIS 7.0.</span></span> <span data-ttu-id="5fcf6-130">在检查后**ASP.NET**，你的屏幕应类似下图。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-130">After checking **ASP.NET**, your screen should look like the following illustration.</span></span>  
  
 <span data-ttu-id="5fcf6-131">![Asp.NET 所需设置](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")</span><span class="sxs-lookup"><span data-stu-id="5fcf6-131">![Asp.NET required settings](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")</span></span>  
  
 <span data-ttu-id="5fcf6-132">这是最小的环境，这两个 wcf 和[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]应用程序中的工作[!INCLUDE[iisver](../../../../includes/iisver-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-132">This is the minimal environment for both WCF and [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] applications to work in [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span></span>  
  
## <a name="iis-70-installation-with-iis-60-compatibility-components"></a><span data-ttu-id="5fcf6-133">IIS 7.0：带 IIS 6.0 兼容组件的安装</span><span class="sxs-lookup"><span data-stu-id="5fcf6-133">IIS 7.0: Installation with IIS 6.0 Compatibility Components</span></span>  
 <span data-ttu-id="5fcf6-134">在安装时[!INCLUDE[iisver](../../../../includes/iisver-md.md)]具有 Visual Studio 2005 或某些其他自动化的脚本或工具 （如 Adsutil.vbs) 配置虚拟应用程序使用的系统上[!INCLUDE[iis601](../../../../includes/iis601-md.md)]元数据库 API，一定要检查[!INCLUDE[iis601](../../../../includes/iis601-md.md)] **脚本工具**。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-134">When installing [!INCLUDE[iisver](../../../../includes/iisver-md.md)] on a system with Visual Studio 2005 or some other automation scripts or tools (such as Adsutil.vbs) that configure virtual applications that use [!INCLUDE[iis601](../../../../includes/iis601-md.md)] Metabase API, ensure that you check the [!INCLUDE[iis601](../../../../includes/iis601-md.md)]**Scripting Tools**.</span></span> <span data-ttu-id="5fcf6-135">这将自动检查其他子节点[!INCLUDE[iis601](../../../../includes/iis601-md.md)]**管理兼容性**。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-135">This automatically checks the other sub-nodes of [!INCLUDE[iis601](../../../../includes/iis601-md.md)]**Management Compatibility**.</span></span> <span data-ttu-id="5fcf6-136">下面的插图显示此操作完成后的屏幕。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-136">The following illustration shows the screen after this is done.</span></span>  
  
 <span data-ttu-id="5fcf6-137">![IIS 6.0 管理兼容性设置](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")</span><span class="sxs-lookup"><span data-stu-id="5fcf6-137">![IIS 6.0 Management Compatibility Settings](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")</span></span>  
  
 <span data-ttu-id="5fcf6-138">使用此安装时，您可以使用所需的所有内容[!INCLUDE[iisver](../../../../includes/iisver-md.md)]，[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]和 WCF 功能和示例可在 Web 上找到。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-138">With this installation, you have everything required to use [!INCLUDE[iisver](../../../../includes/iisver-md.md)], [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] and WCF features and samples available on the Web.</span></span>  
  
## <a name="request-limits"></a><span data-ttu-id="5fcf6-139">请求限制</span><span class="sxs-lookup"><span data-stu-id="5fcf6-139">Request Limits</span></span>  
 <span data-ttu-id="5fcf6-140">在带有 IIS 7 的 [!INCLUDE[wv](../../../../includes/wv-md.md)] 上，`maxUri` 和 `maxQueryStringSize` 设置的默认值均已更改。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-140">On [!INCLUDE[wv](../../../../includes/wv-md.md)] with IIS 7 the default value of the `maxUri` and `maxQueryStringSize` settings have been changed.</span></span> <span data-ttu-id="5fcf6-141">默认情况下，IIS 7.0 中的请求筛选功能允许 URL 的长度为 4096 个字符，查询字符串的长度为 2048 个字符。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-141">By default, request filtering in IIS 7.0 allows a URL length of 4096 characters and a query string length of 2048 characters.</span></span> <span data-ttu-id="5fcf6-142">更改这些默认值，可将以下 XML 添加到 App.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="5fcf6-142">To change these defaults add the following XML to your App.config file.</span></span>  
  
 `<system.webServer>`  
  
 `<security>`  
  
 `<requestFiltering>`  
  
 `<requestLimits maxUrl="8192" maxQueryString="8192" />`  
  
 `</requestFiltering>`  
  
 `</security>`  
  
 `</system.webServer>`  
  
## <a name="see-also"></a><span data-ttu-id="5fcf6-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="5fcf6-143">See Also</span></span>  
 [<span data-ttu-id="5fcf6-144">WAS 激活体系结构</span><span class="sxs-lookup"><span data-stu-id="5fcf6-144">WAS Activation Architecture</span></span>](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)  
 [<span data-ttu-id="5fcf6-145">配置 WAS 以用于 WCF</span><span class="sxs-lookup"><span data-stu-id="5fcf6-145">Configuring WAS for Use with WCF</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)  
 [<span data-ttu-id="5fcf6-146">如何：安装和配置 WCF 激活组件</span><span class="sxs-lookup"><span data-stu-id="5fcf6-146">How to: Install and Configure WCF Activation Components</span></span>](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)  
 [<span data-ttu-id="5fcf6-147">Windows Server App Fabric 承载功能</span><span class="sxs-lookup"><span data-stu-id="5fcf6-147">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)
