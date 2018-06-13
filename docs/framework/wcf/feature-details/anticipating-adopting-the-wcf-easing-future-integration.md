---
title: 预期采用 Windows Communication Foundation：便于以后集成
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: f81e158a5e7f897307c0c6d376dfe01dac127ead
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489591"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a>预期采用 Windows Communication Foundation：便于以后集成
如果你现在使用 ASP.NET，并预期在将来使用 WCF，本主题提供指导可确保新的 ASP.NET Web 服务，将很好地与 WCF 应用程序一起正常工作。  
  
## <a name="general-recommendations"></a>一般性建议  
 对任何新服务采用 ASP.NET 2.0。 这样做将允许新服务访问新版本中的改进和增强。 但是，它还允许可能会出现在同一个应用程序中使用 ASP.NET 2.0 组件以及 WCF 组件。  
  
## <a name="protocols"></a>协议  
 使用 ASP.NET 2.0 的新工具验证与 WS-I 基本配置文件 1.1 的一致性：  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 符合 WS 的 ASP.NET Web 服务的基本配置文件 1.1 可互操作与 WCF 客户端通过会使用 WCF 预定义绑定， <xref:System.ServiceModel.BasicHttpBinding>。  
  
## <a name="service-development"></a>服务开发  
 避免使用 <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> 特性依据 SOAP 消息正文元素的完全限定名称将消息路由到方法，而应使用 SOAPAction HTTP 标头。 WCF 使用 SOAPAction HTTP 标头来路由消息。  
  
## <a name="data-representation"></a>数据表示形式  
 只要为 XML 显式定义了命名空间，则在默认情况下，<xref:System.Xml.Serialization.XmlSerializer> 将类型序列化为的 XML 与 <xref:System.Runtime.Serialization.DataContractSerializer> 将类型序列化为的 XML 在语义上完全相同。 当在将来预期采用 WCF 定义与 ASP.NET Web 服务一起使用的数据类型，可执行以下操作：  
  
1.  使用 .NET Framework 类而不是 XML 架构来定义该类型。  
  
2.  仅将 <xref:System.SerializableAttribute> 和 <xref:System.Xml.Serialization.XmlRootAttribute> 添加到该类，使用后者显式定义类型的命名空间。 不要添加 <xref:System.Xml.Serialization> 命名空间中的其他属性来控制如何将 .NET Framework 类转换为 XML。  
  
 通过采用此方法，以后可将 .NET 类转换为附加了 <xref:System.Runtime.Serialization.DataContractAttribute> 和 <xref:System.Runtime.Serialization.DataMemberAttribute> 的数据协定，而无需为了传输而对类序列化成的 XML 进行重大更改。 将能够作为数据协定由 WCF 应用程序进行处理的消息中由 ASP.NET Web 服务使用的类型这样做，需要在其他好处，更好的性能 WCF 应用程序之间。  
  
## <a name="security"></a>安全性  
 避免使用 Internet Information Services (IIS) 提供的身份验证选项。 WCF 客户端不支持这些选项。 如果服务需要进行保护，使用 WCF 提供的因为这些选项更丰富，并且基于标准协议的选项。  
  
## <a name="see-also"></a>请参阅  
 [预期采用 Windows Communication Foundation：便于以后迁移](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
