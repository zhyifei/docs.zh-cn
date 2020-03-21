---
title: 如何：使用配置来添加 ASP.NET AJAX 终结点
ms.date: 03/30/2017
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
ms.openlocfilehash: 5314bb000371ee2d3eef2576e1edfa455aa65b90
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184838"
---
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a>如何：使用配置来添加 ASP.NET AJAX 终结点
Windows 通信基础 （WCF） 允许您创建一个服务，使启用ASP.NET AJAX 的终结点可用，可以从客户端网站上的 JavaScript 调用。 要创建此类终结点，可以使用配置文件（与所有其他 Windows 通信基础 （WCF） 终结点一样），也可以使用不需要任何配置元素的方法。 本主题演示配置方法。  
  
 使服务终结点ASP.NET启用 AJAX 的过程包括将终结点配置为使用<xref:System.ServiceModel.WebHttpBinding>和 添加[\<启用WebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)终结点行为。 配置终结点后，实现和托管服务的步骤与任何 WCF 服务使用的步骤类似。 有关工作示例，请参阅使用[HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)的 AJAX 服务。  
  
 有关如何在不使用配置的情况下配置ASP.NET AJAX 终结点的详细信息，请参阅[：添加ASP.NET AJAX 终结点而不使用配置](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)。  
  
## <a name="to-create-a-basic-wcf-service"></a>创建基本 WCF 服务  
  
1. 定义具有带有<xref:System.ServiceModel.ServiceContractAttribute>属性标记的接口的基本 WCF 服务协定。 用 <xref:System.ServiceModel.OperationContractAttribute> 标记每个操作。 确保设置 <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> 属性。  
  
    ```csharp
    [ServiceContract(Namespace = "MyService")]  
    public interface ICalculator  
    {  
        [OperationContract]  
         // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. 使用 `ICalculator` 实现 `CalculatorService` 服务协定。  
  
    ```csharp
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }
        // Other operations omitted…
    }
    ```  
  
3. 定义 `ICalculator` 和 `CalculatorService` 实现的命名空间，方法是将它们放置在一个命名空间块中。  
  
    ```csharp
    namespace Microsoft.Ajax.Samples
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
## <a name="to-create-an-aspnet-ajax-endpoint-for-the-service"></a>创建服务的 ASP.NET AJAX 终结点  
  
1. 创建行为配置并指定[\<启用WebScript>ASP.NET](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)启用AJAX的服务终结点的行为。  
  
    ```xml  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="AspNetAjaxBehavior">  
                    <enableWebScript />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
    </system.serviceModel>  
    ```  
  
2. 为使用 <xref:System.ServiceModel.WebHttpBinding> 和前面的步骤中定义的 ASP.NET AJAX 行为的服务创建终结点。  
  
    ```xml  
    <system.serviceModel>  
        <services>  
            <service name="Microsoft.Ajax.Samples.CalculatorService">  
                <endpoint address=""  
                    behaviorConfiguration="AspNetAjaxBehavior"
                    binding="webHttpBinding"  
                    contract="Microsoft.Ajax.Samples.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>
    ```  
  
## <a name="to-host-the-service-in-iis"></a>在 IIS 中承载服务  
  
1. 若要在 IIS 中承载服务，请使用应用程序中的 .svc 扩展创建名为 service 的新文件。 通过添加服务的相应[\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)指令信息来编辑此文件。 例如，`CalculatorService` 示例的服务文件中的内容包含以下信息。  
  
    ```
    <%@ServiceHost
    language=c#
    Debug="true"
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2. 有关在 IIS 中托管的详细信息，请参阅[如何：在 IIS 中托管 WCF 服务](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)。  
  
## <a name="to-call-the-service"></a>调用服务  
  
1. 终结点在相对于 .svc 文件的空地址进行配置，因此服务现在可用，可以通过向 service.svc/\<操作> - 例如，用于`Add`操作的服务.svc/Add 来调用。 可以通过在 ASP.NET AJAX 脚本管理器控件的脚本集合中输入终结点 URL 来使用它。 例如，请参阅[使用 HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)的 AJAX 服务。  
  
## <a name="see-also"></a>另请参阅

- [为 ASP.NET AJAX 创建 WCF 服务](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [如何：将支持 AJAX 的 ASP.NET Web 服务迁移到 WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
