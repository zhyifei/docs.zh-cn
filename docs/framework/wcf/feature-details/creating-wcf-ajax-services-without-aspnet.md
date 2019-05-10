---
title: 创建不使用 ASP.NET 的 WCF AJAX 服务
ms.date: 03/30/2017
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
ms.openlocfilehash: de7e5dc075a821518928514be532ea1940c1ff17
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64627119"
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a>创建不使用 ASP.NET 的 WCF AJAX 服务
Windows Communication Foundation (WCF) AJAX 服务可以从任何支持 JavaScript 的网页，访问而无需 ASP.NET AJAX。 本主题介绍如何创建 WCF 服务。  
  
 有关使用 ASP.NET AJAX 的 WCF 的说明，请参阅[适用于 ASP.NET AJAX 创建 WCF 服务](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)。  
  
 有三个部分创建的 WCF AJAX 服务：  
  
- 创建一个可以从浏览器中访问的 AJAX 终结点。  
  
- 创建一个与 AJAX 兼容的服务协定。  
  
- 访问 WCF AJAX 服务。  
  
## <a name="creating-an-ajax-endpoint"></a>创建 AJAX 终结点  
 若要启用 WCF 服务中的 AJAX 支持的最基本方法是使用<xref:System.ServiceModel.Activation.WebServiceHostFactory>关联服务，如以下示例所示的.svc 文件中。  
  
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
  
 此操作是使用 HTTP POST 到可访问`http://serviceaddress/endpointaddress/GetCities`并返回一条 XML 消息。  
  
 可以使用完整的 Web 编程模型来自定义这些基本方面。 例如，可以使用 <xref:System.ServiceModel.Web.WebGetAttribute> 或 <xref:System.ServiceModel.Web.WebInvokeAttribute> 特性来控制操作响应的 HTTP 谓词，或使用各个特性的 `UriTemplate` 属性来指定自定义 URI。 有关详细信息，请参阅[WCF Web HTTP 编程模型](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)主题。  
  
 AJAX 服务中经常使用 JSON 数据格式。 若要创建返回 JSON 而非 XML 的操作，请将 <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A>（或 <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>）属性设置为 <xref:System.ServiceModel.Web.WebMessageFormat.Json>。 [独立 JSON 序列化](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)主题演示如何内置.NET 类型和数据协定类型映射到 JSON。  
  
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
 WCF AJAX 终结点始终接受 JSON 和 XML 请求。  
  
 内容类型为"application/json"的 HTTP POST 请求将被视为 JSON，并具有内容类型指示 XML (例如，"text/xml") 将被视为 XML。  
  
 HTTP GET 请求的所有请求参数都包含在 URL 本身中。  
  
 用户将负责决定如何创建对终结点的 HTTP 请求。 另外，用户还可以完全控制如何构造构成请求主体的 JSON。 从 JavaScript 中创建的请求的示例，请参阅[具有 JSON 和 XML 的 AJAX 服务](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md)。
