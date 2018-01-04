---
title: "Windows Communication Foundation 使用展望：使未来迁移轻而易举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 76770eff76a7a641ee853f314b5d2c14a56737c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a><span data-ttu-id="16c40-102">Windows Communication Foundation 使用展望：使未来迁移轻而易举</span><span class="sxs-lookup"><span data-stu-id="16c40-102">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>
<span data-ttu-id="16c40-103">要确保将来将新的 ASP.NET 应用程序轻而易举地迁移到 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]，请遵循之前提出的建议以及下面的建议。</span><span class="sxs-lookup"><span data-stu-id="16c40-103">To ensure an easier future migration of new ASP.NET applications to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], follow the preceding recommendations as well as the following recommendations.</span></span>  
  
## <a name="protocols"></a><span data-ttu-id="16c40-104">协议</span><span class="sxs-lookup"><span data-stu-id="16c40-104">Protocols</span></span>  
 <span data-ttu-id="16c40-105">禁用 ASP.NET 2.0 对 SOAP 1.2 的支持：</span><span class="sxs-lookup"><span data-stu-id="16c40-105">Disable ASP.NET 2.0’s support for SOAP 1.2:</span></span>  
  
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
  
 <span data-ttu-id="16c40-106">建议进行此操作，因为 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 要求符合不同协议（如 SOAP 1.1 和 SOAP 1.2）的消息都可以通过使用不同的终结点进行传输。</span><span class="sxs-lookup"><span data-stu-id="16c40-106">Doing so is advisable because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires messages conforming to different protocols, like SOAP 1.1 and SOAP 1.2, to go by using different endpoints.</span></span> <span data-ttu-id="16c40-107">如果将 ASP.NET 2.0 Web 服务配置为同时支持 SOAP 1.1 和 SOAP 1.2（该配置为默认配置），则不能将它向前迁移到原始地址处的单个 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 终结点，毫无疑问，该地址与所有 ASP.NET Web 服务的现有客户端相兼容。</span><span class="sxs-lookup"><span data-stu-id="16c40-107">If an ASP.NET 2.0 Web service is configured to support both SOAP 1.1 and SOAP 1.2, which is the default configuration, then it cannot be migrated forward to a single [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint at the original address that would be certainly be compatible with all of the ASP.NET Web service’s existing clients.</span></span> <span data-ttu-id="16c40-108">另外，选择 SOAP 1.2 而非 SOAP 1.1 将更加严格地限制服务的客户。</span><span class="sxs-lookup"><span data-stu-id="16c40-108">Also choosing SOAP 1.2 instead of 1.1 will more severely restrict the clientele of the service.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="16c40-109">服务开发</span><span class="sxs-lookup"><span data-stu-id="16c40-109">Service Development</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="16c40-110"> 允许您通过将 <xref:System.ServiceModel.ServiceContractAttribute> 应用到接口或类来定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="16c40-110"> allows you to define service contracts by applying the <xref:System.ServiceModel.ServiceContractAttribute> either to interfaces or to classes.</span></span> <span data-ttu-id="16c40-111">建议将此属性应用于接口而不是类，因为这样可以为可由任意数量的类以不同方式实现的协定创建一个定义。</span><span class="sxs-lookup"><span data-stu-id="16c40-111">It is recommended to apply the attribute to an interface rather than to a class, because doing so creates a definition of a contract that can be variously implemented by any number of classes.</span></span> <span data-ttu-id="16c40-112">ASP.NET 2.0 支持将 <xref:System.Web.Services.WebService> 属性应用到接口和类的选项。</span><span class="sxs-lookup"><span data-stu-id="16c40-112">ASP.NET 2.0 supports the option of applying the <xref:System.Web.Services.WebService> attribute to interfaces as well as classes.</span></span> <span data-ttu-id="16c40-113">但是，如前所述，ASP.NET 2.0 中存在缺陷，如果将 <xref:System.Web.Services.WebService> 属性应用到接口而不是类，则此属性的 Namespace 参数将不起任何作用。</span><span class="sxs-lookup"><span data-stu-id="16c40-113">However, as mentioned already, there is a defect in ASP.NET 2.0, by which the Namespace parameter of the <xref:System.Web.Services.WebService> attribute has no effect when that attribute is applied to an interface rather than a class.</span></span> <span data-ttu-id="16c40-114">由于通常建议您使用 <xref:System.Web.Services.WebService> 属性的 Namespace 参数来修改服务的命名空间的默认值 (http://tempuri.org)，因此您应该通过将 <xref:System.ServiceModel.ServiceContractAttribute> 属性应用到接口或类来继续定义 ASP.NET Web 服务。</span><span class="sxs-lookup"><span data-stu-id="16c40-114">Since it is generally advisable to modify the namespace of a service from the default value, http://tempuri.org, using the Namespace parameter of the <xref:System.Web.Services.WebService> attribute, one should continue defining ASP.NET Web Services by applying the <xref:System.ServiceModel.ServiceContractAttribute> attribute either to interfaces or to classes.</span></span>  
  
-   <span data-ttu-id="16c40-115">在定义那些接口的方法中尽量少使用代码。</span><span class="sxs-lookup"><span data-stu-id="16c40-115">Have as little code as possible in the methods by which those interfaces are defined.</span></span> <span data-ttu-id="16c40-116">允许它们将其工作委托给其他类。</span><span class="sxs-lookup"><span data-stu-id="16c40-116">Have them delegate their work to other classes.</span></span> <span data-ttu-id="16c40-117">随后，新的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务类型也可以将其大量的工作委托给那些类。</span><span class="sxs-lookup"><span data-stu-id="16c40-117">New [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service types could then also delegate their substantive work to those classes.</span></span>  
  
-   <span data-ttu-id="16c40-118">使用 `MessageName` 的 <xref:System.Web.Services.WebMethodAttribute> 参数为服务的操作提供显式名称。</span><span class="sxs-lookup"><span data-stu-id="16c40-118">Provide explicit names for the operations of a service using the `MessageName` parameter of the <xref:System.Web.Services.WebMethodAttribute>.</span></span>  
  
    ```  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     <span data-ttu-id="16c40-119">此操作很重要，因为 ASP.NET 中的操作的默认名称与 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 提供的默认名称不同。</span><span class="sxs-lookup"><span data-stu-id="16c40-119">Doing so is important, because the default names for operations in ASP.NET are different from the default names supplied by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="16c40-120">通过提供显式名称，可以避免依赖默认名称。</span><span class="sxs-lookup"><span data-stu-id="16c40-120">By providing explicit names, you avoid relying on the default ones.</span></span>  
  
-   <span data-ttu-id="16c40-121">不要使用多态方法来实现 ASP.NET Web 服务操作，因为 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 并不支持使用多态方法实现操作。</span><span class="sxs-lookup"><span data-stu-id="16c40-121">Do not implement ASP.NET Web service operations with polymorphic methods, because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not support implementing operations with polymorphic methods.</span></span>  
  
-   <span data-ttu-id="16c40-122">使用 <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> 为 SOAPAction HTTP 标头提供显式值，HTTP 请求将通过此标头路由到方法。</span><span class="sxs-lookup"><span data-stu-id="16c40-122">Use the <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> to provide explicit values for the SOAPAction HTTP headers by which HTTP requests will be routed to methods.</span></span>  
  
    ```  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     <span data-ttu-id="16c40-123">采用此方法可摆脱对 ASP.NET 所使用的 SOAPAction 默认值的依赖，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 也是如此。</span><span class="sxs-lookup"><span data-stu-id="16c40-123">Taking this approach will circumvent having to rely on the default SOAPAction values used by ASP.NET and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] being the same.</span></span>  
  
-   <span data-ttu-id="16c40-124">避免使用 SOAP 扩展。</span><span class="sxs-lookup"><span data-stu-id="16c40-124">Avoid using SOAP extensions.</span></span> <span data-ttu-id="16c40-125">如果需要使用 SOAP 扩展，则要确定使用扩展的目的是否为 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 已提供的功能。</span><span class="sxs-lookup"><span data-stu-id="16c40-125">If SOAP extensions are required, then determine whether the purpose for which they are being considered is a feature that is already provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="16c40-126">如果情况确实如此，则重新考虑该选择以立即放弃采用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="16c40-126">If that is indeed the case, then reconsider the choice to not adopt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] right away.</span></span>  
  
## <a name="state-management"></a><span data-ttu-id="16c40-127">状态管理</span><span class="sxs-lookup"><span data-stu-id="16c40-127">State Management</span></span>  
 <span data-ttu-id="16c40-128">避免必须在服务中保持状态。</span><span class="sxs-lookup"><span data-stu-id="16c40-128">Avoid having to maintain state in services.</span></span> <span data-ttu-id="16c40-129">不仅是因为保持状态会降低应用程序的可伸缩性，而且 ASP.NET 和 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的状态管理机制截然不同（虽然在 ASP.NET 兼容模式中 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 确实支持 ASP.NET 机制）。</span><span class="sxs-lookup"><span data-stu-id="16c40-129">Not only does maintaining state tend to compromise the scalability of an application, but the state management mechanisms of ASP.NET and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are very different, although [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does support the ASP.NET mechanisms in ASP.NET compatibility mode.</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="16c40-130">异常处理</span><span class="sxs-lookup"><span data-stu-id="16c40-130">Exception Handling</span></span>  
 <span data-ttu-id="16c40-131">在设计服务发送和接收的数据类型的结构时，请同时设计表示异常的不同类型的结构，这些异常可能发生在人们希望传送到客户端的服务中。</span><span class="sxs-lookup"><span data-stu-id="16c40-131">In designing the structures of the data types to be sent and received by a service, also design structures to represent the various types of exceptions that might occur within a service that one might wish to convey to a client.</span></span>  
  
```  
[Serializable]  
[XmlRoot(  
     Namespace="ExplicitNamespace", IsNullable=true)]  
    public partial class AnticipatedException {  
  
     private string anticipatedExceptionInformationField;  
  
     public string AnticipatedExceptionInformation {  
      get {  
          return this.anticipatedExceptionInformationField;  
          }  
      set {  
          this.anticipatedExceptionInformationField = value;  
          }  
     }  
}  
```  
  
 <span data-ttu-id="16c40-132">使这些类能够将其自身序列化为 XML：</span><span class="sxs-lookup"><span data-stu-id="16c40-132">Give such classes the ability to serialize themselves to XML:</span></span>  
  
```  
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
  
 <span data-ttu-id="16c40-133">然后，可使用这些类为显式引发的 <xref:System.Web.Services.Protocols.SoapException> 实例提供详细信息：</span><span class="sxs-lookup"><span data-stu-id="16c40-133">The classes can then be used to provide the details for explicitly thrown <xref:System.Web.Services.Protocols.SoapException> instances:</span></span>  
  
```  
AnctipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 <span data-ttu-id="16c40-134">可随时重用这些异常类并结合 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.ServiceModel.FaultException%601> 类来引发新的 `FaultException<AnticipatedException>(anticipatedException);`</span><span class="sxs-lookup"><span data-stu-id="16c40-134">These exception classes will be readily reusable with the[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.ServiceModel.FaultException%601> class to throw a new `FaultException<AnticipatedException>(anticipatedException);`</span></span>  
  
## <a name="security"></a><span data-ttu-id="16c40-135">安全性</span><span class="sxs-lookup"><span data-stu-id="16c40-135">Security</span></span>  
 <span data-ttu-id="16c40-136">下面是一些安全建议。</span><span class="sxs-lookup"><span data-stu-id="16c40-136">The following are some security recommendations.</span></span>  
  
-   <span data-ttu-id="16c40-137">避免使用 ASP.NET 2.0 配置文件，因为在将服务迁移到 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 时使用它们将限制对 ASP.NET 集成模式的使用。</span><span class="sxs-lookup"><span data-stu-id="16c40-137">Avoid using ASP.NET 2.0 Profiles, as using them would restrict the use of ASP.NET Integration Mode if the service was migrated to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
-   <span data-ttu-id="16c40-138">避免使用 ACL 来控制对服务的访问，因为 ASP.NET Web 服务支持使用 Internet 信息服务 (IIS) 的 ACL，而 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 却不支持（因为 ASP.NET Web 服务依赖 IIS 进行承载，而 WCF 则无需在 IIS 中进行承载）。</span><span class="sxs-lookup"><span data-stu-id="16c40-138">Avoid using ACLs to control access to services, as ASP.NET Web services supports ACLs using Internet Information Services (IIS), [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not—because ASP.NET Web services depend on IIS for hosting, and WCF does not necessarily have to be hosted in IIS.</span></span>  
  
-   <span data-ttu-id="16c40-139">请务必考虑使用 ASP.NET 2.0 角色提供程序来授权对服务资源的访问。</span><span class="sxs-lookup"><span data-stu-id="16c40-139">Do consider using ASP.NET 2.0 Role Providers for authorizing access to the resources of a service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16c40-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="16c40-140">See Also</span></span>  
 [<span data-ttu-id="16c40-141">预期采用 Windows Communication Foundation：便于以后集成</span><span class="sxs-lookup"><span data-stu-id="16c40-141">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
