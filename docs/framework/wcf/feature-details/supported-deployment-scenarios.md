---
title: 支持的部署方案的 WCF
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: 2da55176cbfe618b332f2df210e3e1c0516b17ae
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2019
ms.locfileid: "67170041"
---
# <a name="supported-deployment-scenarios"></a><span data-ttu-id="352a2-102">支持的部署方案</span><span class="sxs-lookup"><span data-stu-id="352a2-102">Supported deployment scenarios</span></span>

<span data-ttu-id="352a2-103">支持在部分受信任的应用程序中使用的 Windows Communication Foundation (WCF) 功能子集旨在满足使用 WCF 部分，而不是所有方案的要求。</span><span class="sxs-lookup"><span data-stu-id="352a2-103">The subset of Windows Communication Foundation (WCF) features supported for use in partially trusted applications is designed to meet the requirements of some, but not all, scenarios for using WCF.</span></span> <span data-ttu-id="352a2-104">在服务器上，WCF 满足 Internet 规模出于安全原因设置共享托管提供商在 ASP.NET 2.0 中等信任权限运行第三方应用程序的要求。</span><span class="sxs-lookup"><span data-stu-id="352a2-104">On the server, WCF meets the requirements of Internet-scale shared hosting providers who run third-party applications in the ASP.NET 2.0 Medium Trust permission set for security reasons.</span></span> <span data-ttu-id="352a2-105">在客户端，WCF 部分信任支持旨在满足的要求的部署技术如[ClickOnce 部署](/visualstudio/deployment/clickonce-security-and-deployment)或 WPF 的 XAML 浏览器应用程序技术，允许无缝和安全地部署来自不受信任的站点的桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="352a2-105">On the client, WCF partial trust support is designed to meet the requirements of deployment technologies such as [ClickOnce Deployment](/visualstudio/deployment/clickonce-security-and-deployment) or WPF's XAML Browser Application technology, which allow seamless and secure deployment of desktop applications from untrusted sites.</span></span>

## <a name="minimum-permission-requirements"></a><span data-ttu-id="352a2-106">最小权限要求</span><span class="sxs-lookup"><span data-stu-id="352a2-106">Minimum permission requirements</span></span>

<span data-ttu-id="352a2-107">WCF 支持以下标准命名的权限集下运行的应用程序中的功能子集：</span><span class="sxs-lookup"><span data-stu-id="352a2-107">WCF supports a subset of features in applications running under either of the following standard named permission sets:</span></span>

- <span data-ttu-id="352a2-108">“中等信任”权限</span><span class="sxs-lookup"><span data-stu-id="352a2-108">Medium Trust permissions</span></span>

- <span data-ttu-id="352a2-109">“Internet 区域”权限</span><span class="sxs-lookup"><span data-stu-id="352a2-109">Internet Zone permissions</span></span>

<span data-ttu-id="352a2-110">尝试使用 WCF 在部分受信任应用程序中使用限制性更强的权限可能会导致在运行时的安全异常。</span><span class="sxs-lookup"><span data-stu-id="352a2-110">Attempting to use WCF in partially trusted applications with more restrictive permissions may result in security exceptions at runtime.</span></span>

<span data-ttu-id="352a2-111">有关这些权限集支持的功能的详细信息，请参阅 [Partial Trust Feature Compatibility](partial-trust-feature-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="352a2-111">For more information about the features supported in these permission sets, see [Partial Trust Feature Compatibility](partial-trust-feature-compatibility.md).</span></span>

## <a name="partial-trust-on-the-server"></a><span data-ttu-id="352a2-112">在服务器上的部分信任</span><span class="sxs-lookup"><span data-stu-id="352a2-112">Partial trust on the server</span></span>

<span data-ttu-id="352a2-113">托管服务的 ASP.NET Web 应用程序的许多商业提供程序托管在其服务器上运行的应用程序运行在 ASP.NET 2.0 中等信任权限集。</span><span class="sxs-lookup"><span data-stu-id="352a2-113">Many commercial providers of ASP.NET Web application hosting services mandate that applications running on their servers run in the ASP.NET 2.0 Medium Trust permission set.</span></span> <span data-ttu-id="352a2-114">WCF 服务可以在这些环境中运行，前提是它们使用<xref:System.ServiceModel.BasicHttpBinding>，则<xref:System.ServiceModel.WebHttpBinding>，或<xref:System.ServiceModel.WSHttpBinding>具有传输级安全性。</span><span class="sxs-lookup"><span data-stu-id="352a2-114">WCF services can run in these environments provided they use the <xref:System.ServiceModel.BasicHttpBinding>, the <xref:System.ServiceModel.WebHttpBinding>, or the <xref:System.ServiceModel.WSHttpBinding> with transport-level security.</span></span>

<span data-ttu-id="352a2-115">在中等信任宿主环境中运行的 WCF 服务也可用作中间层服务通过将消息发送到客户端请求的响应中的其他服务器。</span><span class="sxs-lookup"><span data-stu-id="352a2-115">WCF services running in Medium Trust hosting environments can also act as middle-tier services by sending messages to other servers in response to client requests.</span></span> <span data-ttu-id="352a2-116">如果宿主环境已授予应用程序适当的 <xref:System.Net.WebPermission> 以向所需服务器发出出站请求，则支持服务器上的中间层方案。</span><span class="sxs-lookup"><span data-stu-id="352a2-116">Middle-tier scenarios on the server are supported if the hosting environment has granted the application the appropriate <xref:System.Net.WebPermission> to make outbound requests to the desired server.</span></span>

<span data-ttu-id="352a2-117">除了 SOAP 消息使用的受支持的 SOAP 绑定之一，WCF 还支持<xref:System.ServiceModel.WebHttpBinding>构建在部分受信任的应用程序中的 Web 样式服务。</span><span class="sxs-lookup"><span data-stu-id="352a2-117">In addition to SOAP messaging using one of the supported SOAP bindings, WCF supports the <xref:System.ServiceModel.WebHttpBinding> for building Web-style services in partially trusted applications.</span></span> <span data-ttu-id="352a2-118">[WCF Web HTTP 编程模型](wcf-web-http-programming-model.md)， [WCF 联合](wcf-syndication.md)，并[AJAX 集成和 JSON 支持](ajax-integration-and-json-support.md)WCF 的功能支持在部分信任环境中。</span><span class="sxs-lookup"><span data-stu-id="352a2-118">The [WCF Web HTTP Programming Model](wcf-web-http-programming-model.md), [WCF Syndication](wcf-syndication.md), and [AJAX Integration and JSON Support](ajax-integration-and-json-support.md) features of WCF are all supported in partial trust.</span></span>

<span data-ttu-id="352a2-119">工作流服务需要完全信任权限并且不能在部分受信任的应用程序中使用。</span><span class="sxs-lookup"><span data-stu-id="352a2-119">Workflow Services require Full Trust permissions and cannot be used in partially trusted applications.</span></span>

<span data-ttu-id="352a2-120">有关详细信息，请参阅[如何：ASP.NET 2.0 中使用中等信任](https://go.microsoft.com/fwlink/?LinkId=84603)。</span><span class="sxs-lookup"><span data-stu-id="352a2-120">For more information, see [How to: Use Medium Trust in ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=84603).</span></span>

## <a name="partial-trust-on-the-client"></a><span data-ttu-id="352a2-121">在客户端上的部分信任</span><span class="sxs-lookup"><span data-stu-id="352a2-121">Partial trust on the client</span></span>

<span data-ttu-id="352a2-122">在从不受信任的 Internet 网站上下载和运行代码时必须采用某些安全预防措施。</span><span class="sxs-lookup"><span data-stu-id="352a2-122">Certain security precautions must be taken when downloading and running code from untrusted Internet sites.</span></span> <span data-ttu-id="352a2-123">这两[ClickOnce 部署](/visualstudio/deployment/clickonce-security-and-deployment)和 WPF 的 XAML 浏览器应用程序 (XBAP) 技术都可以使用部分信任以对授予受限的权限 （Internet 区域） 不受信任的代码。</span><span class="sxs-lookup"><span data-stu-id="352a2-123">Both [ClickOnce Deployment](/visualstudio/deployment/clickonce-security-and-deployment) and WPF's XAML Browser Application (XBAP) technology make use of partial trust to grant limited permissions (Internet Zone) to untrusted code.</span></span>

<span data-ttu-id="352a2-124">可以使用 WCF 与从部分受信任通过以下任一方法部署的应用程序中的远程服务器进行通信[ClickOnce 部署](/visualstudio/deployment/clickonce-security-and-deployment)或 xbap 技术。</span><span class="sxs-lookup"><span data-stu-id="352a2-124">WCF can be used to communicate with remote servers from within partially trusted applications deployed by either [ClickOnce Deployment](/visualstudio/deployment/clickonce-security-and-deployment) or XBAP.</span></span> <span data-ttu-id="352a2-125">在 Internet 区域权限集中包含<xref:System.Net.WebPermission>发起主机的允许这些应用程序与使用任何支持的 WCF 绑定中所述与其源服务器进行通信[Partial Trust Feature Compatibility](partial-trust-feature-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="352a2-125">The Internet Zone permission set includes <xref:System.Net.WebPermission> for the originating host, which allows these applications to communicate with their origin server using any of the supported WCF bindings described in [Partial Trust Feature Compatibility](partial-trust-feature-compatibility.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="352a2-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="352a2-126">See also</span></span>

- [<span data-ttu-id="352a2-127">代码访问安全性</span><span class="sxs-lookup"><span data-stu-id="352a2-127">Code Access Security</span></span>](../../misc/code-access-security.md)
- [<span data-ttu-id="352a2-128">Windows Presentation Foundation 浏览器承载的应用程序概述</span><span class="sxs-lookup"><span data-stu-id="352a2-128">Windows Presentation Foundation Browser-Hosted Applications Overview</span></span>](../../wpf/app-development/wpf-xaml-browser-applications-overview.md)
- [<span data-ttu-id="352a2-129">部分信任</span><span class="sxs-lookup"><span data-stu-id="352a2-129">Partial Trust</span></span>](partial-trust.md)
- <span data-ttu-id="352a2-130">[ASP.NET 信任级别和策略文件](https://docs.microsoft.com/previous-versions/wyts434y(v=vs.140))</span><span class="sxs-lookup"><span data-stu-id="352a2-130">[ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/wyts434y(v=vs.140))</span></span>
