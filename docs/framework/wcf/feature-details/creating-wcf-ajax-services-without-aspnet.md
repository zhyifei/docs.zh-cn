---
title: 创建不使用 ASP.NET 的 WCF AJAX 服务
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b652bcd522a8eea81b3d1218fbd054ee0b2caea8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a>创建不使用 ASP.NET 的 WCF AJAX 服务
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] AJAX 服务可以从任何支持 JavaScript 的网页进行访问，而不需要使用 ASP.NET AJAX。 本主题描述如何创建此类 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务。  
  
 有关使用说明[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]与 ASP.NET AJAX，请参阅[为 ASP.NET AJAX 创建 WCF 服务](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)。  
  
 创建 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] AJAX 服务包括三个部分：  
  
-   创建一个可以从浏览器中访问的 AJAX 终结点。  
  
-   创建一个与 AJAX 兼容的服务协定。  
  
-   访问 WCF AJAX 服务。  
  
## <a name="creating-an-ajax-endpoint"></a>创建 AJAX 终结点  
 若要在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务中启用 AJAX 支持，最基本的方法是在与服务关联的 .svc 文件中使用 <xref:System.ServiceModel.Activation.WebServiceHostFactory>，如下面的示例所示。  
  
```  
<%ServiceHost   
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 另外，也可以使用配置来添加 AJAX 终结点。 在服务终结点上使用 <xref:System.ServiceModel.WebHttpBinding>，并使用 <xref:System.ServiceModel.Description.WebHttpBehavior> 配置该终结点，如下面的代码段所示。  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="AjaxBehavior">  
          <webHttp/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Ajax.Samples.CityService">  
        <endpoint   
          address="ajaxEndpoint"  
          behaviorConfiguration="AjaxBehavior"  
          binding="webHttpBinding"  
          contract="Microsoft.Ajax.Samples.ICityService" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 有关工作示例，请参阅[具有 JSON 和 XML 的 AJAX 服务](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md)。  
  
## <a name="creating-an-ajax-compatible-service-contract"></a>创建与 AJAX 兼容的服务协定  
 默认情况下，通过 AJAX 终结点公开的服务协定将以 XML 格式返回数据。 而且，默认情况下，通过对包含跟有操作名称的终结点地址的 URL 发出 HTTP POST 请求，将可以访问服务操作，如下面的示例所示。  
  
```  
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 此操作是使用 HTTP POST 到可以访问`http://serviceaddress/endpointaddress/GetCities`并返回一条 XML 消息。  
  
 可以使用完整的 Web 编程模型来自定义这些基本方面。 例如，可以使用 <xref:System.ServiceModel.Web.WebGetAttribute> 或 <xref:System.ServiceModel.Web.WebInvokeAttribute> 特性来控制操作响应的 HTTP 谓词，或使用各个特性的 `UriTemplate` 属性来指定自定义 URI。 有关详细信息，请参阅[WCF Web HTTP 编程模型](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)主题。  
  
 AJAX 服务中经常使用 JSON 数据格式。 若要创建返回 JSON 而非 XML 的操作，请将 <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A>（或 <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>）属性设置为 <xref:System.ServiceModel.Web.WebMessageFormat.Json>。 [独立 JSON 序列化](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)主题说明如何内置.NET 类型和数据协定类型映射到 JSON。  
  
 通常，JSON 的请求和响应只包括一项。 对于上面的 `GetCities` 操作，该请求将类似于以下语句。  
  
```  
"na"  
```  
  
 该请求的响应类似于以下语句。  
  
```  
["Nairobi", "Naples", "Nashville"]  
```  
  
 如果该操作使用了额外的参数，则请求样式必须是“包装的”，以便将两个参数都包装在一个 JSON 对象中。 下面的示例显示了这种样式的 JSON 消息。  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 下面的协定会接受此消息。  
  
```  
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a>访问 AJAX 服务  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] AJAX 终结点始终接受 JSON 和 XML 请求。  
  
 使用"应用程序/json"的内容类型的 HTTP POST 请求将被视为 JSON，并具有内容类型指示 XML (例如，"文本/xml") 将被视为 XML。  
  
 HTTP GET 请求的所有请求参数都包含在 URL 本身中。  
  
 用户将负责决定如何创建对终结点的 HTTP 请求。 另外，用户还可以完全控制如何构造构成请求主体的 JSON。 从 JavaScript 中创建请求的示例，请参阅[具有 JSON 和 XML 的 AJAX 服务](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md)。
