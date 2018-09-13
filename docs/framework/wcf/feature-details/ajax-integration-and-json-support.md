---
title: AJAX 集成和 JSON 支持
ms.date: 03/30/2017
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
ms.openlocfilehash: bcf1cab9386d9d9503af6258c1bb39f8744c073b
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2018
ms.locfileid: "44709031"
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="85070-102">AJAX 集成和 JSON 支持</span><span class="sxs-lookup"><span data-stu-id="85070-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="85070-103">对 ASP.NET 异步 JavaScript 和 XML (AJAX) 的 Windows Communication Foundation (WCF) 支持，并且 JavaScript 对象表示法 (JSON) 数据格式允许 WCF 服务向 AJAX 客户端公开操作。</span><span class="sxs-lookup"><span data-stu-id="85070-103">The Windows Communication Foundation (WCF) support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow WCF services to expose operations to AJAX clients.</span></span> <span data-ttu-id="85070-104">AJAX 客户端是运行 JavaScript 代码以及使用 HTTP 请求这些 WCF 服务进行访问的网页。</span><span class="sxs-lookup"><span data-stu-id="85070-104">AJAX clients are Web pages running JavaScript code and accessing these WCF services using HTTP requests.</span></span> <span data-ttu-id="85070-105">本节中的主题提供有关此支持以及如何实现此支持的信息。</span><span class="sxs-lookup"><span data-stu-id="85070-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 <span data-ttu-id="85070-106">详细了解 ASP.NET AJAX 和及其与 ASP.NET 2.0 的集成，请参阅[ASP.NET AJAX 概述](https://go.microsoft.com/fwlink/?LinkId=96725)。</span><span class="sxs-lookup"><span data-stu-id="85070-106">For more information about ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](https://go.microsoft.com/fwlink/?LinkId=96725).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="85070-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="85070-107">In This Section</span></span>  
 [<span data-ttu-id="85070-108">为 ASP.NET AJAX 创建 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="85070-108">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="85070-109">描述如何 WCF 服务可以公开到 AJAX 客户端通过添加相应的 AJAX 终结点是通过配置或使用自定义以生成将自动配置 AJAX 终结点的服务主机的服务主机工厂。</span><span class="sxs-lookup"><span data-stu-id="85070-109">Describes how an WCF service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="85070-110">创建不使用 ASP.NET 的 WCF AJAX 服务</span><span class="sxs-lookup"><span data-stu-id="85070-110">Creating WCF AJAX Services without ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="85070-111">介绍如何不使用 ASP.NET 创建的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="85070-111">Describes how to create an WCF service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="85070-112">支持 JSON 和其他数据传输格式</span><span class="sxs-lookup"><span data-stu-id="85070-112">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="85070-113">描述对通常用于与 ASP.NET AJAX 服务进行通信的 JSON 格式（替代 XML）的支持。</span><span class="sxs-lookup"><span data-stu-id="85070-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="85070-114">如何：将支持 AJAX 的 ASP.NET Web 服务迁移到 WCF</span><span class="sxs-lookup"><span data-stu-id="85070-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="85070-115">介绍如何将支持 AJAX 的 ASP.NET Web 服务迁移到 WCF Web 服务。</span><span class="sxs-lookup"><span data-stu-id="85070-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a WCF Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85070-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="85070-116">See Also</span></span>  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>  
 [<span data-ttu-id="85070-117">WCF Web HTTP 编程模型</span><span class="sxs-lookup"><span data-stu-id="85070-117">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
