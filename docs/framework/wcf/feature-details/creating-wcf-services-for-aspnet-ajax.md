---
title: "为 ASP.NET AJAX 创建 WCF 服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04c0402c-e617-4ba5-aedf-d17692234776
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 50ce4918689687bfa702f0673d8d2a669abdf541
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="creating-wcf-services-for-aspnet-ajax"></a><span data-ttu-id="04e0b-102">为 ASP.NET AJAX 创建 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="04e0b-102">Creating WCF Services for ASP.NET AJAX</span></span>
<span data-ttu-id="04e0b-103">使用 Microsoft ASP.NET AJAX，可以通过快速响应的熟悉用户界面元素快速创建包括丰富用户体验的网页。</span><span class="sxs-lookup"><span data-stu-id="04e0b-103">Microsoft ASP.NET AJAX enables you to quickly create Web pages that include a rich user experience with responsive and familiar user interface elements.</span></span> <span data-ttu-id="04e0b-104">ASP.NET AJAX 提供了并入跨浏览器 ECMAScript (JavaScript) 和动态 HTML (DHTML) 技术的客户端脚本库，并将其与基于 ASP.NET 2.0 服务器的开发平台集成在一起。</span><span class="sxs-lookup"><span data-stu-id="04e0b-104">ASP.NET AJAX provides client-script libraries that incorporate cross-browser ECMAScript (JavaScript) and dynamic HTML (DHTML) technologies, and it integrates them with the ASP.NET 2.0 server-based development platform.</span></span> <span data-ttu-id="04e0b-105">通过使用 ASP.NET AJAX，可以改进用户体验和 Web 应用程序的效率。</span><span class="sxs-lookup"><span data-stu-id="04e0b-105">By using ASP.NET AJAX, you can improve the user experience and the efficiency of your Web applications.</span></span>  
  
 <span data-ttu-id="04e0b-106">ASP.NET AJAX 由客户端脚本库和集成的服务器组件组成，以提供稳定的开发框架。</span><span class="sxs-lookup"><span data-stu-id="04e0b-106">ASP.NET AJAX consists of client-script libraries and of server components that are integrated to provide a robust development framework.</span></span> <span data-ttu-id="04e0b-107">从 ASP.NET 页访问服务：将服务 URL 添加到页上的 ASP.NET 脚本管理器控件后，就可以使用看起来与常规 JavaScript 函数调用完全相同的 JavaScript 代码调用服务操作。</span><span class="sxs-lookup"><span data-stu-id="04e0b-107">To access a service from an ASP.NET page: once the service URL is added to the ASP.NET Script Manager control on the page, service operations may be invoked using JavaScript code that looks exactly like a regular JavaScript function call.</span></span> <span data-ttu-id="04e0b-108">请参阅[了解 ASP.NET AJAX](http://go.microsoft.com/fwlink/?LinkId=186475)有关 AJAX 框架内的 Web 服务使用。</span><span class="sxs-lookup"><span data-stu-id="04e0b-108">See [Learn ASP.NET AJAX](http://go.microsoft.com/fwlink/?LinkId=186475) about the use of Web services within the AJAX framework.</span></span>  
  
 <span data-ttu-id="04e0b-109">通过添加相应的 ASP.NET AJAX 终结点，可以将大多数 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务作为与 ASP.NET AJAX 兼容的服务公开。</span><span class="sxs-lookup"><span data-stu-id="04e0b-109">Most [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services may be exposed as a service compatible with ASP.NET AJAX by adding an appropriate ASP.NET AJAX endpoint.</span></span>  
  
 <span data-ttu-id="04e0b-110">如果使用 Visual Studio，你可以使用启用了 AJAX 的 WCF 服务中, 可用的预建的模板**添加新项**处理 ASP.NET 网站或 Web 应用程序时的对话框。</span><span class="sxs-lookup"><span data-stu-id="04e0b-110">If you are using Visual Studio, you may use a pre-built template for AJAX-enabled WCF services, available in the **Add New Item** dialog when working with ASP.NET Web Sites or Web Applications.</span></span>  
  
 <span data-ttu-id="04e0b-111">如果未使用 Visual Studio 模板，则创建 ASP.NET AJAX 终结点有以下两种方法：</span><span class="sxs-lookup"><span data-stu-id="04e0b-111">If you are not using the Visual Studio templates, there are two ways to create an ASP.NET AJAX endpoint:</span></span>  
  
-   <span data-ttu-id="04e0b-112">使用动态主机激活（而不使用任何配置）创建终结点。</span><span class="sxs-lookup"><span data-stu-id="04e0b-112">Create the endpoint using dynamic host activation without using any configuration.</span></span> <span data-ttu-id="04e0b-113">如果您不熟悉 WCF 配置系统，则这是最基本的方法。</span><span class="sxs-lookup"><span data-stu-id="04e0b-113">This is the most basic approach if you are unfamiliar with the WCF configuration system.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="04e0b-114">[如何： 添加 ASP.NET AJAX 终结点而不使用配置](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="04e0b-114"> [How to: Add an ASP.NET AJAX Endpoint Without Using Configuration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span></span>  
  
-   <span data-ttu-id="04e0b-115">使用配置将启用了 AJAX 的终结点添加到 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="04e0b-115">Add an AJAX-enabled endpoint to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service using configuration.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="04e0b-116">[如何： 使用配置来添加 ASP.NET AJAX 终结点](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)。</span><span class="sxs-lookup"><span data-stu-id="04e0b-116"> [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).</span></span>  
  
 <span data-ttu-id="04e0b-117">Web 编程模型中所述[WCF Web HTTP 编程模型概述](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)可能的 ASP.NET AJAX 服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="04e0b-117">The Web Programming Model described in the [WCF Web HTTP Programming Model Overview](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md) may be used with ASP.NET AJAX services.</span></span> <span data-ttu-id="04e0b-118">尤其是在下列情况下：</span><span class="sxs-lookup"><span data-stu-id="04e0b-118">Specifically:</span></span>  
  
-   <span data-ttu-id="04e0b-119">可以使用 <xref:System.ServiceModel.Web.WebGetAttribute> 和 <xref:System.ServiceModel.Web.WebInvokeAttribute> 属性在 HTTP GET 和 HTTP POST 动词之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="04e0b-119">You can use the <xref:System.ServiceModel.Web.WebGetAttribute> and <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes to select between HTTP GET and HTTP POST verbs.</span></span> <span data-ttu-id="04e0b-120">如果正确使用它们，则这可能会大大提高应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="04e0b-120">If used correctly, this may significantly improve your application’s performance.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="04e0b-121">[How to： 之间 HTTP POST 和 HTTP GET 请求进行选择 ASP.NET AJAX 终结点](../../../../docs/framework/wcf/feature-details/http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="04e0b-121"> [How to: Choose between HTTP POST and HTTP GET requests for ASP.NET AJAX Endpoints](../../../../docs/framework/wcf/feature-details/http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md).</span></span>  
  
-   <span data-ttu-id="04e0b-122">可以使用 <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> 和 <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> 属性使服务返回 XML 数据而不是默认的 JavaScript 对象表示法 (JSON)。</span><span class="sxs-lookup"><span data-stu-id="04e0b-122">You can use the <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> and <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> properties to cause your service to return XML data instead of the default JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="04e0b-123">使用 ASP.NET AJAX 框架执行此操作可导致 JavaScript 客户端接收 XML DOM 对象。</span><span class="sxs-lookup"><span data-stu-id="04e0b-123">Doing this with the ASP.NET AJAX framework causes the JavaScript client to receive an XML DOM object.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="04e0b-124">您的操作必须将内容类型设置为文本/xml 才能生效。</span><span class="sxs-lookup"><span data-stu-id="04e0b-124">Your operation must set the content type to text/xml for this to work.</span></span> <span data-ttu-id="04e0b-125">否则，JavaScript 客户端会接收包含 XML 的字符串而不是 XML DOM 对象。</span><span class="sxs-lookup"><span data-stu-id="04e0b-125">Otherwise, the JavaScript client will receive a string containing the XML instead of an XML DOM object.</span></span>  
  
     <span data-ttu-id="04e0b-126">下面是返回正确设置了内容类型的 XML 数据的操作示例：</span><span class="sxs-lookup"><span data-stu-id="04e0b-126">The following is an example of an operation that returns XML data with the content type set appropriately:</span></span>  
  
    ```  
    [OperationContract, WebGet(ResponseFormat=WebMessageFormat.Xml)]  
    public XElement GetData()  
    {  
    XElement x;  
    //Get some data here...  
  
    WebOperationContext.Current.OutgoingResponse.ContentType = "text/xml";      
    return x;  
    }  
    ```  
  
-   <span data-ttu-id="04e0b-127">如果要求与 ASP.NET AJAX 兼容，则不能更改 <xref:System.ServiceModel.Web.WebGetAttribute> 和 <xref:System.ServiceModel.Web.WebInvokeAttribute> 特性上的任何其他属性。</span><span class="sxs-lookup"><span data-stu-id="04e0b-127">No other properties on the <xref:System.ServiceModel.Web.WebGetAttribute> and <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes can be changed if compatibility with ASP.NET AJAX is required.</span></span> <span data-ttu-id="04e0b-128">只要不违反 ASP.NET AJAX 调用约定，就可以使用 Web 编程模型的其他方面。</span><span class="sxs-lookup"><span data-stu-id="04e0b-128">Other aspects of the Web Programming Model can be used as long as the ASP.NET AJAX calling conventions are not violated.</span></span>  
  
 <span data-ttu-id="04e0b-129">更高级的方案要求了解 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中 AJAX 支持的某些其他详细信息：</span><span class="sxs-lookup"><span data-stu-id="04e0b-129">More advanced scenarios require some additional details of AJAX support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] be understood:</span></span>  
  
-   <span data-ttu-id="04e0b-130">若要了解如何将数据传输之间的 AJAX 页客户端和[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]服务中使用 JavaScript 和.NET Framework 类型如何映射到 JavaScript 类型的详细信息，请参阅[支持 JSON 和其他数据传输格式](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md).</span><span class="sxs-lookup"><span data-stu-id="04e0b-130">To understand how data is transferred between an AJAX page client and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service using JavaScript, and for details on how .NET Framework types map to JavaScript types, see [Support for JSON and Other Data Transfer Formats](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md).</span></span>  
  
-   <span data-ttu-id="04e0b-131">若要利用 ASP.NET 功能（例如，基于 URL 的身份验证和访问 ASP.NET 会话信息），可能希望通过配置启用 ASP.NET 兼容性模式。</span><span class="sxs-lookup"><span data-stu-id="04e0b-131">To take advantage of ASP.NET features, for example, URL-based authentication and accessing the ASP.NET session information, you may want to enable the ASP.NET Compatibility Mode through configuration.</span></span>  
  
 <span data-ttu-id="04e0b-132">甚至在没有 ASP.NET AJAX 框架时，也可能使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中的 AJAX 终结点。</span><span class="sxs-lookup"><span data-stu-id="04e0b-132">AJAX endpoints in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] may even be consumed without the ASP.NET AJAX framework.</span></span> <span data-ttu-id="04e0b-133">执行此操作需要了解 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中 AJAX 支持的支持体系结构。</span><span class="sxs-lookup"><span data-stu-id="04e0b-133">Doing so requires an understanding of the support architecture of AJAX support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="04e0b-134">有关此体系结构的讨论，请参阅[WCF Web HTTP 编程对象模型](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="04e0b-134">For a discussion of this architecture, see [WCF Web HTTP Programming Object Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md).</span></span> <span data-ttu-id="04e0b-135">有关演示此方法的代码示例，请参阅[具有 JSON 和 XML 的 AJAX 服务](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="04e0b-135">For a code sample demonstrating this approach, see the [AJAX Service with JSON and XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04e0b-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04e0b-136">See Also</span></span>  
 [<span data-ttu-id="04e0b-137">WCF Web HTTP 编程模型</span><span class="sxs-lookup"><span data-stu-id="04e0b-137">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="04e0b-138">如何： 添加 ASP.NET AJAX 终结点而不使用配置</span><span class="sxs-lookup"><span data-stu-id="04e0b-138">How to: Add an ASP.NET AJAX Endpoint Without Using Configuration</span></span>](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)  
 [<span data-ttu-id="04e0b-139">如何： 使用配置来添加 ASP.NET AJAX 终结点</span><span class="sxs-lookup"><span data-stu-id="04e0b-139">How to: Use Configuration to Add an ASP.NET AJAX Endpoint</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)  
 [<span data-ttu-id="04e0b-140">如何： 之间 HTTP POST 和 HTTP GET 请求进行选择 ASP.NET AJAX 终结点</span><span class="sxs-lookup"><span data-stu-id="04e0b-140">How to: Choose between HTTP POST and HTTP GET requests for ASP.NET AJAX Endpoints</span></span>](../../../../docs/framework/wcf/feature-details/http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md)
