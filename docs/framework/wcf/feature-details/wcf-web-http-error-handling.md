---
title: "WCF Web HTTP 错误处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02891563-0fce-4c32-84dc-d794b1a5c040
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3366ab851c6e6b66a5df94bdb24baad4ae0c8d14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="wcf-web-http-error-handling"></a><span data-ttu-id="5ae0b-102">WCF Web HTTP 错误处理</span><span class="sxs-lookup"><span data-stu-id="5ae0b-102">WCF Web HTTP Error Handling</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="5ae0b-103"> Web HTTP 错误处理可用于从 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web HTTP 服务返回指定 HTTP 状态代码的错误，并且返回的错误详细信息使用与操作相同的格式（如 XML 或 JSON）。</span><span class="sxs-lookup"><span data-stu-id="5ae0b-103"> Web HTTP error handling enables you to return errors from [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web HTTP services that specify an HTTP status code and return error details using the same format as the operation (for example, XML or JSON).</span></span>  
  
## <a name="wcf-web-http-error-handling"></a><span data-ttu-id="5ae0b-104">WCF Web HTTP 错误处理</span><span class="sxs-lookup"><span data-stu-id="5ae0b-104">WCF Web HTTP Error Handling</span></span>  
 <span data-ttu-id="5ae0b-105"><xref:System.ServiceModel.Web.WebFaultException> 类定义可用于指定 HTTP 状态代码的构造函数。</span><span class="sxs-lookup"><span data-stu-id="5ae0b-105">The <xref:System.ServiceModel.Web.WebFaultException> class defines a constructor that allows you to specify an HTTP status code.</span></span> <span data-ttu-id="5ae0b-106">随后会将此状态代码返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="5ae0b-106">This status code is then returned to the client.</span></span> <span data-ttu-id="5ae0b-107"><xref:System.ServiceModel.Web.WebFaultException> 类的泛型版本 <xref:System.ServiceModel.Web.WebFaultException%601> 可用于返回用户定义的类型，该类型中包含有关所出现错误的信息。</span><span class="sxs-lookup"><span data-stu-id="5ae0b-107">A generic version of the <xref:System.ServiceModel.Web.WebFaultException> class, <xref:System.ServiceModel.Web.WebFaultException%601> enables you to return a user-defined type that contains information about the error that occurred.</span></span> <span data-ttu-id="5ae0b-108">将使用由操作指定的格式序列化此自定义对象，并将它返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="5ae0b-108">This custom object is serialized using the format specified by the operation and returned to the client.</span></span> <span data-ttu-id="5ae0b-109">下面的示例演示如何返回 HTTP 状态代码。</span><span class="sxs-lookup"><span data-stu-id="5ae0b-109">The following example shows how to return an HTTP status code.</span></span>  
  
```  
Public string Operation1()  
{   // Operation logic  
   // ...  
   Throw new WebFaultException(HttpStatusCode.Forbidden);  
}  
```  
  
 <span data-ttu-id="5ae0b-110">下面的示例演示如何在用户定义的类型中返回 HTTP 状态代码和额外信息。</span><span class="sxs-lookup"><span data-stu-id="5ae0b-110">The following example shows how to return an HTTP status code and extra information in a user-defined type.</span></span> <span data-ttu-id="5ae0b-111">`MyErrorDetail` 是用户定义的类型，其中包含有关所出现错误的额外信息。</span><span class="sxs-lookup"><span data-stu-id="5ae0b-111">`MyErrorDetail` is a user-defined type that contains extra information about the error that occurred.</span></span>  
  
```  
Public string Operation2()  
   // Operation logic  
   // ...   MyErrorDetail detail = new MyErrorDetail  
   {  
      Message = "Error Message",  
      ErrorCode = 123,  
   }  
   throw new WebFaultException<MyErrorDetail>(detail, HttpStatusCode.Forbidden);  
}  
```  
  
 <span data-ttu-id="5ae0b-112">上述代码返回 HTTP 响应，其中包括禁止状态代码以及包含 `MyErrorDetails` 对象实例的正文。</span><span class="sxs-lookup"><span data-stu-id="5ae0b-112">The preceding code returns an HTTP response with the forbidden status code and a body that contains an instance of the `MyErrorDetails` object.</span></span> <span data-ttu-id="5ae0b-113">`MyErrorDetails` 对象的格式由以下内容确定：</span><span class="sxs-lookup"><span data-stu-id="5ae0b-113">The format of the `MyErrorDetails` object is determined by:</span></span>  
  
-   <span data-ttu-id="5ae0b-114">服务操作指定的 `ResponseFormat` 或 <xref:System.ServiceModel.Web.WebGetAttribute> 特性的 <xref:System.ServiceModel.Web.WebInvokeAttribute> 参数值。</span><span class="sxs-lookup"><span data-stu-id="5ae0b-114">The value of the `ResponseFormat` parameter of the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute specified on the service operation.</span></span>  
  
-   <span data-ttu-id="5ae0b-115"><xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A> 的值。</span><span class="sxs-lookup"><span data-stu-id="5ae0b-115">The value of <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.</span></span>  
  
-   <span data-ttu-id="5ae0b-116">通过访问 <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> 得到的 <xref:System.ServiceModel.Web.OutgoingWebResponseContext> 属性值。</span><span class="sxs-lookup"><span data-stu-id="5ae0b-116">The value of the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> property by accessing the <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5ae0b-117">如何将这些值会影响操作的格式设置，请参阅[WCF Web HTTP 格式设置](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)。</span><span class="sxs-lookup"><span data-stu-id="5ae0b-117"> how these values affect the formatting of the operation, see [WCF Web HTTP Formatting](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>  
  
 <span data-ttu-id="5ae0b-118"><xref:System.ServiceModel.Web.WebFaultException> 是一个 <xref:System.ServiceModel.FaultException>，因此可用作公开 SOAP 终结点和 Web HTTP 终结点的服务的错误异常编程模型。</span><span class="sxs-lookup"><span data-stu-id="5ae0b-118"><xref:System.ServiceModel.Web.WebFaultException> is a <xref:System.ServiceModel.FaultException> and therefore can be used as the fault exception programming model for services that expose SOAP endpoints as well as web HTTP endpoints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ae0b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ae0b-119">See Also</span></span>  
 [<span data-ttu-id="5ae0b-120">WCF Web HTTP 编程模型</span><span class="sxs-lookup"><span data-stu-id="5ae0b-120">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="5ae0b-121">WCF Web HTTP 格式设置</span><span class="sxs-lookup"><span data-stu-id="5ae0b-121">WCF Web HTTP Formatting</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)  
 [<span data-ttu-id="5ae0b-122">定义和指定错误</span><span class="sxs-lookup"><span data-stu-id="5ae0b-122">Defining and Specifying Faults</span></span>](../../../../docs/framework/wcf/defining-and-specifying-faults.md)  
 [<span data-ttu-id="5ae0b-123">处理异常和错误</span><span class="sxs-lookup"><span data-stu-id="5ae0b-123">Handling Exceptions and Faults</span></span>](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)  
 [<span data-ttu-id="5ae0b-124">发送和接收错误</span><span class="sxs-lookup"><span data-stu-id="5ae0b-124">Sending and Receiving Faults</span></span>](../../../../docs/framework/wcf/sending-and-receiving-faults.md)
