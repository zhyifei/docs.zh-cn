---
title: 如何：使用配置来添加 ASP.NET AJAX 终结点
ms.date: 03/30/2017
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
ms.openlocfilehash: db5085d01dbed841109ac46fe4e8b2a0143352e3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337612"
---
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a><span data-ttu-id="cd7cd-102">如何：使用配置来添加 ASP.NET AJAX 终结点</span><span class="sxs-lookup"><span data-stu-id="cd7cd-102">How to: Use Configuration to Add an ASP.NET AJAX Endpoint</span></span>
<span data-ttu-id="cd7cd-103">Windows Communication Foundation (WCF)，可创建可支持 ASP.NET AJAX 的终结点可用，可从调用 JavaScript 客户端 Web 站点上的服务。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-103">Windows Communication Foundation (WCF) allows you to create a service that makes an ASP.NET AJAX-enabled endpoint available that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="cd7cd-104">若要创建这样的终结点，可以使用配置文件，因为与所有其他 Windows Communication Foundation (WCF) 终结点，或使用不需要任何配置元素的方法。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-104">To create such an endpoint, you can either use a configuration file, as with all other Windows Communication Foundation (WCF) endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="cd7cd-105">本主题演示配置方法。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-105">This topic demonstrates the configuration approach.</span></span>  
  
 <span data-ttu-id="cd7cd-106">配置要使用的终结点包含的过程，可让服务终结点成为支持 ASP.NET AJAX 的一部分<xref:System.ServiceModel.WebHttpBinding>并添加[ \<enableWebScript >](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)终结点行为。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-106">The part of the procedure that enables the service endpoint to become ASP.NET AJAX-enabled consists of configuring the endpoint to use the <xref:System.ServiceModel.WebHttpBinding> and to add the [\<enableWebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) endpoint behavior.</span></span> <span data-ttu-id="cd7cd-107">配置终结点之后, 实现和承载服务的步骤是类似于所使用的任何 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-107">After configuring the endpoint, the steps to implement and host the service are similar to those used by any WCF service.</span></span> <span data-ttu-id="cd7cd-108">有关工作示例，请参阅[使用 HTTP POST 的 AJAX 服务](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-108">For a working example, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
 <span data-ttu-id="cd7cd-109">有关如何配置 ASP.NET AJAX 终结点而不使用配置的详细信息，请参阅[如何：添加 ASP.NET AJAX 终结点而不使用配置](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-109">For more information about how to configure an ASP.NET AJAX endpoint without using configuration, see [How to: Add an ASP.NET AJAX Endpoint Without Using Configuration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span></span>  
  
### <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="cd7cd-110">创建基本 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="cd7cd-110">To create a basic WCF service</span></span>  
  
1. <span data-ttu-id="cd7cd-111">使用标记的接口定义基本的 WCF 服务约定<xref:System.ServiceModel.ServiceContractAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-111">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="cd7cd-112">用 <xref:System.ServiceModel.OperationContractAttribute> 标记每个操作。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-112">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="cd7cd-113">确保设置 <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-113">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
    ```  
    [ServiceContract(Namespace = "MyService")]  
    public interface ICalculator  
    {  
        [OperationContract]  
         // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. <span data-ttu-id="cd7cd-114">使用 `ICalculator` 实现 `CalculatorService` 服务协定。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-114">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
    ```  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3. <span data-ttu-id="cd7cd-115">定义 `ICalculator` 和 `CalculatorService` 实现的命名空间，方法是将它们放置在一个命名空间块中。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-115">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-create-an-aspnet-ajax-endpoint-for-the-service"></a><span data-ttu-id="cd7cd-116">创建服务的 ASP.NET AJAX 终结点</span><span class="sxs-lookup"><span data-stu-id="cd7cd-116">To create an ASP.NET AJAX endpoint for the service</span></span>  
  
1. <span data-ttu-id="cd7cd-117">创建行为配置，并指定[ \<enableWebScript >](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)支持 ASP.NET AJAX 的终结点的服务的行为。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-117">Create a behavior configuration and specify the [\<enableWebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior for ASP.NET AJAX-enabled endpoints of the service.</span></span>  
  
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
  
2. <span data-ttu-id="cd7cd-118">为使用 <xref:System.ServiceModel.WebHttpBinding> 和前面的步骤中定义的 ASP.NET AJAX 行为的服务创建终结点。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-118">Create an endpoint for the service that uses the <xref:System.ServiceModel.WebHttpBinding> and the ASP.NET AJAX behavior defined in the previous step.</span></span>  
  
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
  
### <a name="to-host-the-service-in-iis"></a><span data-ttu-id="cd7cd-119">在 IIS 中承载服务</span><span class="sxs-lookup"><span data-stu-id="cd7cd-119">To host the service in IIS</span></span>  
  
1. <span data-ttu-id="cd7cd-120">若要在 IIS 中承载服务，请使用应用程序中的 .svc 扩展创建名为 service 的新文件。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-120">To host the service in IIS, create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="cd7cd-121">编辑此文件添加适当的[ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)服务指令信息。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-121">Edit this file by adding the appropriate [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="cd7cd-122">例如，`CalculatorService` 示例的服务文件中的内容包含以下信息。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-122">For example, the content in the service file for the `CalculatorService` sample contains the following information.</span></span>  
  
    ```  
    <%@ServiceHost   
    language=c#   
    Debug="true"   
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2. <span data-ttu-id="cd7cd-123">有关在 IIS 中承载的详细信息，请参阅[如何：承载在 IIS 中的 WCF 服务](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-123">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
### <a name="to-call-the-service"></a><span data-ttu-id="cd7cd-124">调用服务</span><span class="sxs-lookup"><span data-stu-id="cd7cd-124">To call the service</span></span>  
  
1. <span data-ttu-id="cd7cd-125">相对于.svc 文件的空地址处配置的终结点，因此该服务现已推出，可以在调用将请求发送到 service.svc/\<操作 >-例如，便`Add`操作。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-125">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="cd7cd-126">可以通过在 ASP.NET AJAX 脚本管理器控件的脚本集合中输入终结点 URL 来使用它。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-126">You can use it by entering the endpoint URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="cd7cd-127">有关示例，请参阅[使用 HTTP POST 的 AJAX 服务](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)。</span><span class="sxs-lookup"><span data-stu-id="cd7cd-127">For an example, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd7cd-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd7cd-128">See also</span></span>

- [<span data-ttu-id="cd7cd-129">为 ASP.NET AJAX 创建 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="cd7cd-129">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="cd7cd-130">如何：将启用了 AJAX 的 ASP.NET Web 服务迁移到 WCF</span><span class="sxs-lookup"><span data-stu-id="cd7cd-130">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
