---
title: Windows Communication Foundation 使用展望：使未来迁移轻而易举
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: 995bdaaaba96bf8697ea75c1f1a17fa8e51ec2d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185476"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Windows Communication Foundation 使用展望：使未来迁移轻而易举
为确保新的ASP.NET应用程序更容易将来迁移到 WCF，请遵循前面的建议以及以下建议。  
  
## <a name="protocols"></a>协议  
 禁用 ASP.NET 2.0 对 SOAP 1.2 的支持：  
  
```xml  
<configuration>  
     <system.web>  
      <webServices >  
          <protocols>  
           <remove name="HttpSoap12"/>  
          </protocols>
      </webServices>  
     </system.web>
</configuration>  
```  
  
 这样做是可取的，因为 WCF 要求符合不同协议（如 SOAP 1.1 和 SOAP 1.2）的消息使用不同的终结点。 如果 ASP.NET 2.0 Web 服务配置为同时支持 SOAP 1.1 和 SOAP 1.2（这是默认配置），则无法将其向前迁移到原始地址的单个 WCF 终结点，该终结点肯定与所有ASP.NET Web 兼容服务的现有客户端。 另外，选择 SOAP 1.2 而非 SOAP 1.1 将更加严格地限制服务的客户。  
  
## <a name="service-development"></a>服务开发  
 WCF 允许您通过将 服务协定应用于<xref:System.ServiceModel.ServiceContractAttribute>接口或类来定义服务协定。 建议将此属性应用于接口而不是类，因为这样可以为可由任意数量的类以不同方式实现的协定创建一个定义。 ASP.NET 2.0 支持将 <xref:System.Web.Services.WebService> 属性应用到接口和类的选项。 但是，如前所述，ASP.NET 2.0 中存在缺陷，如果将 <xref:System.Web.Services.WebService> 属性应用到接口而不是类，则此属性的 Namespace 参数将不起任何作用。 由于通常建议使用`http://tempuri.org`<xref:System.Web.Services.WebService>属性的 Namespace 参数修改服务的命名空间，因此应该继续通过将<xref:System.ServiceModel.ServiceContractAttribute>该属性应用于接口或类来定义ASP.NET Web 服务。  
  
- 在定义那些接口的方法中尽量少使用代码。 允许它们将其工作委托给其他类。 然后，新的 WCF 服务类型也可以将其实质性工作委托给这些类。  
  
- 使用 `MessageName` 的 <xref:System.Web.Services.WebMethodAttribute> 参数为服务的操作提供显式名称。  
  
    ```csharp  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     这样做很重要，因为ASP.NET操作的默认名称与 WCF 提供的默认名称不同。 通过提供显式名称，可以避免依赖默认名称。  
  
- 不要使用多态方法实现ASP.NET Web 服务操作，因为 WCF 不支持使用多态方法实现操作。  
  
- 使用 <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> 为 SOAPAction HTTP 标头提供显式值，HTTP 请求将通过此标头路由到方法。  
  
    ```csharp  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     采用此方法将规避依赖于 ASP.NET 和 WCF 使用的默认 SOAPAction 值的解决方法。  
  
- 避免使用 SOAP 扩展。 如果需要 SOAP 扩展，则确定考虑扩展的目的是否为 WCF 已经提供的功能。 如果确实如此，那么重新考虑不马上采用WCF的选择。  
  
## <a name="state-management"></a>状态管理  
 避免必须在服务中保持状态。 维护状态不仅会损害应用程序的可伸缩性，而且ASP.NET和 WCF 的状态管理机制也大不相同，尽管 WCF 确实支持ASP.NET兼容性模式下的ASP.NET机制。  
  
## <a name="exception-handling"></a>异常处理  
 在设计服务发送和接收的数据类型的结构时，请同时设计表示异常的不同类型的结构，这些异常可能发生在人们希望传送到客户端的服务中。  
  
```csharp  
[Serializable]  
[XmlRoot(Namespace="ExplicitNamespace", IsNullable=true)]  
public partial class AnticipatedException
{
    private string anticipatedExceptionInformationField;  

    public string AnticipatedExceptionInformation
    {  
        get {
            return this.anticipatedExceptionInformationField;  
        }  
        set {  
            this.anticipatedExceptionInformationField = value;  
        }  
    }  
}  
```  
  
 使这些类能够将其自身序列化为 XML：  
  
```csharp  
public XmlNode ToXML()  
{  
     XmlSerializer serializer = new XmlSerializer(  
      typeof(AnticipatedException));  
     MemoryStream memoryStream = new MemoryStream();  
     XmlTextWriter writer = new XmlTextWriter(  
     memoryStream, UnicodeEncoding.UTF8);  
     serializer.Serialize(writer, this);  
     XmlDocument document = new XmlDocument();  
     document.LoadXml(new string(  
     UnicodeEncoding.UTF8.GetChars(  
     memoryStream.GetBuffer())).Trim());  
    return document.DocumentElement;  
}  
```  
  
 然后，可使用这些类为显式引发的 <xref:System.Web.Services.Protocols.SoapException> 实例提供详细信息：  
  
```csharp  
AnticipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 这些异常类将很容易重用与 WCF<xref:System.ServiceModel.FaultException%601>类，以抛出一个新的`FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>安全性  
 下面是一些安全建议。  
  
- 避免使用ASP.NET 2.0 配置文件，因为如果服务迁移到 WCF，使用这些配置文件将限制ASP.NET集成模式的使用。  
  
- 避免使用 ACL 来控制对服务的访问，因为 ASP.NET Web 服务支持使用 Internet 信息服务 （IIS） 的 ACL），WCF 不支持，因为 ASP.NET Web 服务依赖于 IIS 进行托管，并且 WCF 不一定必须在 IIS 中托管。  
  
- 请务必考虑使用 ASP.NET 2.0 角色提供程序来授权对服务资源的访问。  
  
## <a name="see-also"></a>另请参阅

- [预期采用 Windows Communication Foundation：便于以后集成](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
