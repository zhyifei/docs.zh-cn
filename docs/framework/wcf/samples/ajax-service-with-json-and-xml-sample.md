---
title: "具有 JSON 和 XML 的 AJAX 服务示例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ea5860d-0c42-4ae9-941a-e07efdd8e29c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d831d4663031419977b75c6cfe183ac4bd52a86
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="ajax-service-with-json-and-xml-sample"></a><span data-ttu-id="fe61b-102">具有 JSON 和 XML 的 AJAX 服务示例</span><span class="sxs-lookup"><span data-stu-id="fe61b-102">AJAX Service with JSON and XML Sample</span></span>
<span data-ttu-id="fe61b-103">此示例演示如何使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 来创建异步 JavaScript 和 XML (AJAX) 服务，该服务返回 JavaScript 对象表示法 (JSON) 或 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="fe61b-103">This sample demonstrates how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to create an Asynchronous JavaScript and XML (AJAX) service that returns either JavaScript Object Notation (JSON) or XML data.</span></span> <span data-ttu-id="fe61b-104">可以从 Web 浏览器客户端使用 JavaScript 代码来访问 AJAX 服务。</span><span class="sxs-lookup"><span data-stu-id="fe61b-104">You can access an AJAX service by using JavaScript code from a Web browser client.</span></span> <span data-ttu-id="fe61b-105">此示例基于[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)示例。</span><span class="sxs-lookup"><span data-stu-id="fe61b-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>  
  
 <span data-ttu-id="fe61b-106">与其他 AJAX 示例不同的是，此示例不使用 ASP.NET AJAX 和 <xref:System.Web.UI.ScriptManager> 控件。</span><span class="sxs-lookup"><span data-stu-id="fe61b-106">Unlike the other AJAX samples, this sample does not use ASP.NET AJAX and the <xref:System.Web.UI.ScriptManager> control.</span></span> <span data-ttu-id="fe61b-107">在某个其他配置下，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] AJAX 服务可以从任何 HTML 页面通过 JavaScript 来访问，此处对该方案进行了演示。</span><span class="sxs-lookup"><span data-stu-id="fe61b-107">With some additional configuration, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] AJAX services can be accessed from any HTML page through JavaScript, and this scenario is shown here.</span></span> <span data-ttu-id="fe61b-108">有关使用示例[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]与 ASP.NET AJAX，请参阅[AJAX 示例](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e)。</span><span class="sxs-lookup"><span data-stu-id="fe61b-108">For an example of using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see [AJAX Samples](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
 <span data-ttu-id="fe61b-109">此示例演示如何在 JSON 和 XML 之间切换操作的响应类型。</span><span class="sxs-lookup"><span data-stu-id="fe61b-109">This sample shows how to switch the response type of an operation between JSON and XML.</span></span> <span data-ttu-id="fe61b-110">无论服务是配置为由 ASP.NET AJAX 访问还是由 HTML/JavaScript 客户端页面访问，此功能均可用。</span><span class="sxs-lookup"><span data-stu-id="fe61b-110">This functionality is available regardless of whether the service is configured to be accessed by ASP.NET AJAX or by an HTML/JavaScript client page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe61b-111">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="fe61b-111">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="fe61b-112">为了启用非 ASP.NET AJAX 客户端，请在 .svc 文件中使用 <xref:System.ServiceModel.Activation.WebServiceHostFactory>（而不是 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>）。</span><span class="sxs-lookup"><span data-stu-id="fe61b-112">To enable the use of non-ASP.NET AJAX clients, use <xref:System.ServiceModel.Activation.WebServiceHostFactory> (not <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>) in the .svc file.</span></span> <span data-ttu-id="fe61b-113"><xref:System.ServiceModel.Activation.WebServiceHostFactory> 将 <xref:System.ServiceModel.Description.WebHttpEndpoint> 标准终结点添加到服务中。</span><span class="sxs-lookup"><span data-stu-id="fe61b-113"><xref:System.ServiceModel.Activation.WebServiceHostFactory> adds a <xref:System.ServiceModel.Description.WebHttpEndpoint> standard endpoint to the service.</span></span> <span data-ttu-id="fe61b-114">终结点配置在一个相对于 .svc 文件的空地址；这意味着服务的地址是 http://localhost/ServiceModelSamples/service.svc，除了操作名以外没有其他后缀。</span><span class="sxs-lookup"><span data-stu-id="fe61b-114">The endpoint is configured at an empty address relative to the .svc file; this means that the address of the service is http://localhost/ServiceModelSamples/service.svc, with no additional suffixes other than the operation name.</span></span>  
  
```html  
<%@ServiceHost language="c#" Debug="true" Service="Microsoft.Samples.XmlAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebServiceHostFactory" %>  
```  
  
 <span data-ttu-id="fe61b-115">可以使用 Web.config 中的以下节对终结点进行其他配置更改。</span><span class="sxs-lookup"><span data-stu-id="fe61b-115">The following section in Web.config can be used to make additional configuration changes to the endpoint.</span></span> <span data-ttu-id="fe61b-116">如果不需要额外更改，则可以移除该节。</span><span class="sxs-lookup"><span data-stu-id="fe61b-116">It can be removed if no extra changes are needed.</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <!-- Use this element to configure the endpoint -->  
      <standardEndpoint name="" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="fe61b-117">默认数据格式为<xref:System.ServiceModel.Description.WebHttpEndpoint>时的默认数据格式为 XML，<xref:System.ServiceModel.Description.WebScriptEndpoint>为 JSON。</span><span class="sxs-lookup"><span data-stu-id="fe61b-117">The default data format for <xref:System.ServiceModel.Description.WebHttpEndpoint> is XML, while the default data format for <xref:System.ServiceModel.Description.WebScriptEndpoint> is JSON.</span></span> <span data-ttu-id="fe61b-118">有关详细信息，请参阅[不使用 ASP.NET 创建 WCF AJAX 服务](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)。</span><span class="sxs-lookup"><span data-stu-id="fe61b-118">For more information, see [Creating WCF AJAX Services without ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md).</span></span>  
  
 <span data-ttu-id="fe61b-119">以下示例中的服务是一个标准的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务，它具有两个操作。</span><span class="sxs-lookup"><span data-stu-id="fe61b-119">The service in the following sample is a standard [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service with two operations.</span></span> <span data-ttu-id="fe61b-120">这两个操作都需要针对 <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped> 或 <xref:System.ServiceModel.Web.WebGetAttribute> 属性使用 <xref:System.ServiceModel.Web.WebInvokeAttribute> 正文样式，该样式特定于 `webHttp` 行为，对于 JSON/XML 数据格式开关没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="fe61b-120">Both operations require the <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped> body style on the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes, which is specific to the `webHttp` behavior and has no bearing on the JSON/XML data format switch.</span></span>  
  
```  
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Xml, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathXml(double n1, double n2);  
```  
  
 <span data-ttu-id="fe61b-121">该操作的响应格式指定为 XML，这是默认值设置为[ \<webHttp >](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)行为。</span><span class="sxs-lookup"><span data-stu-id="fe61b-121">The response format for the operation is specified as XML, which is the default setting for the [\<webHttp>](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="fe61b-122">但是，最好显式指定响应格式。</span><span class="sxs-lookup"><span data-stu-id="fe61b-122">However, it is good practice explicitly specify the response format.</span></span>  
  
 <span data-ttu-id="fe61b-123">另一个操作使用 `WebInvokeAttribute` 属性并显式指定响应的 JSON（而不是 XML）。</span><span class="sxs-lookup"><span data-stu-id="fe61b-123">The other operation uses the `WebInvokeAttribute` attribute and explicitly specifies JSON instead of XML for the response.</span></span>  
  
```  
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Json, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathJson(double n1, double n2);  
```  
  
 <span data-ttu-id="fe61b-124">请注意，在这两种情况下，操作均返回一个复杂类型 `MathResult`，该类型是一个标准的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 数据协定类型。</span><span class="sxs-lookup"><span data-stu-id="fe61b-124">Note that in both cases the operations return a complex type, `MathResult`, which is a standard [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] data contract type.</span></span>  
  
 <span data-ttu-id="fe61b-125">客户端网页 XmlAjaxClientPage.htm 包含 JavaScript 代码调用上面的两个操作之一，当用户单击**执行计算 (返回 JSON)**或**执行计算 (返回 XML)**页上的按钮。</span><span class="sxs-lookup"><span data-stu-id="fe61b-125">The client Web page XmlAjaxClientPage.htm contains JavaScript code that invokes one of the preceding two operations when the user clicks the **Perform calculation (return JSON)** or **Perform calculation (return XML)** buttons on the page.</span></span> <span data-ttu-id="fe61b-126">用来调用服务的代码将构造 JSON 正文并使用 HTTP POST 发送它。</span><span class="sxs-lookup"><span data-stu-id="fe61b-126">The code to invoke the service constructs a JSON body and sends it using HTTP POST.</span></span> <span data-ttu-id="fe61b-127">创建请求手动在 JavaScript 中，与不同[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)的示例，并使用 ASP.NET AJAX 的其他示例。</span><span class="sxs-lookup"><span data-stu-id="fe61b-127">The request is created manually in JavaScript, unlike the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample and the other samples using ASP.NET AJAX.</span></span>  
  
```  
// Create HTTP request  
var xmlHttp;  
// Request instantiation code omitted…  
// Result handler code omitted…  
  
// Build the operation URL  
var url = "service.svc/ajaxEndpoint/";  
url = url + operation;  
  
// Build the body of the JSON message  
var body = '{"n1":';  
body = body + document.getElementById("num1").value + ',"n2":';  
body = body + document.getElementById("num2").value + '}';  
  
// Send the HTTP request  
xmlHttp.open("POST", url, true);  
xmlHttp.setRequestHeader("Content-type", "application/json");  
xmlHttp.send(body);  
```  
  
 <span data-ttu-id="fe61b-128">当服务进行响应时，响应将显示出来，而不会在页面上的文本框中进一步执行任何处理。</span><span class="sxs-lookup"><span data-stu-id="fe61b-128">When the service responds, the response is displayed without any further processing in a textbox on the page.</span></span> <span data-ttu-id="fe61b-129">这是为了进行演示而实现的，您可以直接遵循所使用的 XML 和 JSON 数据格式。</span><span class="sxs-lookup"><span data-stu-id="fe61b-129">This is implemented for demonstration purposes to allow you to directly observe the XML and JSON data formats used.</span></span>  
  
```  
// Create result handler   
xmlHttp.onreadystatechange=function(){  
     if(xmlHttp.readyState == 4){  
          document.getElementById("result").value = xmlHttp.responseText;  
     }  
}  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="fe61b-130">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="fe61b-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fe61b-131">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="fe61b-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fe61b-132">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="fe61b-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fe61b-133">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="fe61b-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\XmlAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fe61b-134">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="fe61b-134">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="fe61b-135">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="fe61b-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="fe61b-136">生成解决方案 XmlAjaxService.sln 中所述[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="fe61b-136">Build the solution XmlAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="fe61b-137">定位到 http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm（不要在浏览器中从项目目录中打开 XmlAjaxClientPage.htm）。</span><span class="sxs-lookup"><span data-stu-id="fe61b-137">Navigate to http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm (do not open XmlAjaxClientPage.htm in the browser from the project directory).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe61b-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe61b-138">See Also</span></span>  
 [<span data-ttu-id="fe61b-139">使用 HTTP POST 的 AJAX 服务</span><span class="sxs-lookup"><span data-stu-id="fe61b-139">AJAX Service Using HTTP POST</span></span>](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)
