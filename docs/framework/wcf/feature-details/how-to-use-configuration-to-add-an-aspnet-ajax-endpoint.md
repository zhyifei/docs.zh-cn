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
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a><span data-ttu-id="75647-102">如何：使用配置来添加 ASP.NET AJAX 终结点</span><span class="sxs-lookup"><span data-stu-id="75647-102">How to: Use Configuration to Add an ASP.NET AJAX Endpoint</span></span>
<span data-ttu-id="75647-103">Windows 通信基础 （WCF） 允许您创建一个服务，使启用ASP.NET AJAX 的终结点可用，可以从客户端网站上的 JavaScript 调用。</span><span class="sxs-lookup"><span data-stu-id="75647-103">Windows Communication Foundation (WCF) allows you to create a service that makes an ASP.NET AJAX-enabled endpoint available that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="75647-104">要创建此类终结点，可以使用配置文件（与所有其他 Windows 通信基础 （WCF） 终结点一样），也可以使用不需要任何配置元素的方法。</span><span class="sxs-lookup"><span data-stu-id="75647-104">To create such an endpoint, you can either use a configuration file, as with all other Windows Communication Foundation (WCF) endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="75647-105">本主题演示配置方法。</span><span class="sxs-lookup"><span data-stu-id="75647-105">This topic demonstrates the configuration approach.</span></span>  
  
 <span data-ttu-id="75647-106">使服务终结点ASP.NET启用 AJAX 的过程包括将终结点配置为使用<xref:System.ServiceModel.WebHttpBinding>和 添加[\<启用WebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)终结点行为。</span><span class="sxs-lookup"><span data-stu-id="75647-106">The part of the procedure that enables the service endpoint to become ASP.NET AJAX-enabled consists of configuring the endpoint to use the <xref:System.ServiceModel.WebHttpBinding> and to add the [\<enableWebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) endpoint behavior.</span></span> <span data-ttu-id="75647-107">配置终结点后，实现和托管服务的步骤与任何 WCF 服务使用的步骤类似。</span><span class="sxs-lookup"><span data-stu-id="75647-107">After configuring the endpoint, the steps to implement and host the service are similar to those used by any WCF service.</span></span> <span data-ttu-id="75647-108">有关工作示例，请参阅使用[HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)的 AJAX 服务。</span><span class="sxs-lookup"><span data-stu-id="75647-108">For a working example, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
 <span data-ttu-id="75647-109">有关如何在不使用配置的情况下配置ASP.NET AJAX 终结点的详细信息，请参阅[：添加ASP.NET AJAX 终结点而不使用配置](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="75647-109">For more information about how to configure an ASP.NET AJAX endpoint without using configuration, see [How to: Add an ASP.NET AJAX Endpoint Without Using Configuration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span></span>  
  
## <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="75647-110">创建基本 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="75647-110">To create a basic WCF service</span></span>  
  
1. <span data-ttu-id="75647-111">定义具有带有<xref:System.ServiceModel.ServiceContractAttribute>属性标记的接口的基本 WCF 服务协定。</span><span class="sxs-lookup"><span data-stu-id="75647-111">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="75647-112">用 <xref:System.ServiceModel.OperationContractAttribute> 标记每个操作。</span><span class="sxs-lookup"><span data-stu-id="75647-112">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="75647-113">确保设置 <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="75647-113">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
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
  
2. <span data-ttu-id="75647-114">使用 `ICalculator` 实现 `CalculatorService` 服务协定。</span><span class="sxs-lookup"><span data-stu-id="75647-114">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
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
  
3. <span data-ttu-id="75647-115">定义 `ICalculator` 和 `CalculatorService` 实现的命名空间，方法是将它们放置在一个命名空间块中。</span><span class="sxs-lookup"><span data-stu-id="75647-115">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```csharp
    namespace Microsoft.Ajax.Samples
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
## <a name="to-create-an-aspnet-ajax-endpoint-for-the-service"></a><span data-ttu-id="75647-116">创建服务的 ASP.NET AJAX 终结点</span><span class="sxs-lookup"><span data-stu-id="75647-116">To create an ASP.NET AJAX endpoint for the service</span></span>  
  
1. <span data-ttu-id="75647-117">创建行为配置并指定[\<启用WebScript>ASP.NET](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)启用AJAX的服务终结点的行为。</span><span class="sxs-lookup"><span data-stu-id="75647-117">Create a behavior configuration and specify the [\<enableWebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior for ASP.NET AJAX-enabled endpoints of the service.</span></span>  
  
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
  
2. <span data-ttu-id="75647-118">为使用 <xref:System.ServiceModel.WebHttpBinding> 和前面的步骤中定义的 ASP.NET AJAX 行为的服务创建终结点。</span><span class="sxs-lookup"><span data-stu-id="75647-118">Create an endpoint for the service that uses the <xref:System.ServiceModel.WebHttpBinding> and the ASP.NET AJAX behavior defined in the previous step.</span></span>  
  
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
  
## <a name="to-host-the-service-in-iis"></a><span data-ttu-id="75647-119">在 IIS 中承载服务</span><span class="sxs-lookup"><span data-stu-id="75647-119">To host the service in IIS</span></span>  
  
1. <span data-ttu-id="75647-120">若要在 IIS 中承载服务，请使用应用程序中的 .svc 扩展创建名为 service 的新文件。</span><span class="sxs-lookup"><span data-stu-id="75647-120">To host the service in IIS, create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="75647-121">通过添加服务的相应[\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)指令信息来编辑此文件。</span><span class="sxs-lookup"><span data-stu-id="75647-121">Edit this file by adding the appropriate [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="75647-122">例如，`CalculatorService` 示例的服务文件中的内容包含以下信息。</span><span class="sxs-lookup"><span data-stu-id="75647-122">For example, the content in the service file for the `CalculatorService` sample contains the following information.</span></span>  
  
    ```
    <%@ServiceHost
    language=c#
    Debug="true"
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2. <span data-ttu-id="75647-123">有关在 IIS 中托管的详细信息，请参阅[如何：在 IIS 中托管 WCF 服务](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)。</span><span class="sxs-lookup"><span data-stu-id="75647-123">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
## <a name="to-call-the-service"></a><span data-ttu-id="75647-124">调用服务</span><span class="sxs-lookup"><span data-stu-id="75647-124">To call the service</span></span>  
  
1. <span data-ttu-id="75647-125">终结点在相对于 .svc 文件的空地址进行配置，因此服务现在可用，可以通过向 service.svc/\<操作> - 例如，用于`Add`操作的服务.svc/Add 来调用。</span><span class="sxs-lookup"><span data-stu-id="75647-125">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="75647-126">可以通过在 ASP.NET AJAX 脚本管理器控件的脚本集合中输入终结点 URL 来使用它。</span><span class="sxs-lookup"><span data-stu-id="75647-126">You can use it by entering the endpoint URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="75647-127">例如，请参阅[使用 HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)的 AJAX 服务。</span><span class="sxs-lookup"><span data-stu-id="75647-127">For an example, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75647-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75647-128">See also</span></span>

- [<span data-ttu-id="75647-129">为 ASP.NET AJAX 创建 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="75647-129">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="75647-130">如何：将支持 AJAX 的 ASP.NET Web 服务迁移到 WCF</span><span class="sxs-lookup"><span data-stu-id="75647-130">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
