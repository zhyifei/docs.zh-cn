---
title: "AJAX 集成和 JSON 支持"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4889c88dab77759f854da0069bb300d63ebb1a08
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="35743-102">AJAX 集成和 JSON 支持</span><span class="sxs-lookup"><span data-stu-id="35743-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="35743-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 支持 ASP.NET 异步 JavaScript 和 XML (AJAX)，并且 JavaScript 对象表示法 (JSON) 数据格式允许 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务向 AJAX 客户端公开操作。</span><span class="sxs-lookup"><span data-stu-id="35743-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services to expose operations to AJAX clients.</span></span> <span data-ttu-id="35743-104">AJAX 客户端是运行 JavaScript 代码并使用 HTTP 请求访问这些 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务的网页。</span><span class="sxs-lookup"><span data-stu-id="35743-104">AJAX clients are Web pages running JavaScript code and accessing these [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services using HTTP requests.</span></span> <span data-ttu-id="35743-105">本节中的主题提供有关此支持以及如何实现此支持的信息。</span><span class="sxs-lookup"><span data-stu-id="35743-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="35743-106">ASP.NET AJAX 和的集成与 ASP.NET 2.0，请参阅[ASP.NET AJAX 概述](http://go.microsoft.com/fwlink/?LinkId=96725)。</span><span class="sxs-lookup"><span data-stu-id="35743-106"> ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](http://go.microsoft.com/fwlink/?LinkId=96725).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35743-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="35743-107">In This Section</span></span>  
 [<span data-ttu-id="35743-108">为 ASP.NET AJAX 创建 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="35743-108">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="35743-109">描述如何通过使用配置或服务主机工厂（自定义为生成自动配置 AJAX 终结点的服务主机）添加相应的 AJAX 终结点以将 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务公开到 AJAX 客户端。</span><span class="sxs-lookup"><span data-stu-id="35743-109">Describes how an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="35743-110">创建不使用 ASP.NET 的 WCF AJAX 服务</span><span class="sxs-lookup"><span data-stu-id="35743-110">Creating WCF AJAX Services without ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="35743-111">描述如何在不使用 ASP.NET 的情况下创建 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="35743-111">Describes how to create an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="35743-112">对 JSON 和其他数据传输格式的支持</span><span class="sxs-lookup"><span data-stu-id="35743-112">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="35743-113">描述对通常用于与 ASP.NET AJAX 服务进行通信的 JSON 格式（替代 XML）的支持。</span><span class="sxs-lookup"><span data-stu-id="35743-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="35743-114">如何： 将启用了 AJAX 的 ASP.NET Web 服务迁移到 WCF</span><span class="sxs-lookup"><span data-stu-id="35743-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="35743-115">描述如何将支持 AJAX 的 ASP.NET Web 服务迁移到 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web 服务。</span><span class="sxs-lookup"><span data-stu-id="35743-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35743-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35743-116">See Also</span></span>  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>  
 [<span data-ttu-id="35743-117">WCF Web HTTP 编程模型</span><span class="sxs-lookup"><span data-stu-id="35743-117">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
