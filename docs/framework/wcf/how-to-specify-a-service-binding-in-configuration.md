---
title: "如何：在配置中指定服务绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 885037f7-1c2b-4d7a-90d9-06b89be172f2
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 204ea09a7a6c14188b85f23829fc3a9446aaadd9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-a-service-binding-in-configuration"></a><span data-ttu-id="3dec7-102">如何：在配置中指定服务绑定</span><span class="sxs-lookup"><span data-stu-id="3dec7-102">How to: Specify a Service Binding in Configuration</span></span>
<span data-ttu-id="3dec7-103">在本示例中，为基本计算器服务定义 `ICalculator` 协定，在 `CalculatorService` 类中实现该服务，然后在 Web.config 文件中配置其终结点，该文件中指定此服务使用 <xref:System.ServiceModel.BasicHttpBinding>。</span><span class="sxs-lookup"><span data-stu-id="3dec7-103">In this example, an `ICalculator` contract is defined for a basic calculator service, the service is implemented in the `CalculatorService` class, and then its endpoint is configured in the Web.config file, where it is specified that the service uses the <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="3dec7-104">有关如何配置使用代码而不一种配置此服务的说明，请参阅[如何： 在代码中指定服务绑定](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md)。</span><span class="sxs-lookup"><span data-stu-id="3dec7-104">For a description of how to configure this service using code instead of a configuration, see [How to: Specify a Service Binding in Code](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md).</span></span>  
  
 <span data-ttu-id="3dec7-105">通常，最佳做法是以声明方式在配置中指定绑定和地址信息，而不是在代码中强制指定。</span><span class="sxs-lookup"><span data-stu-id="3dec7-105">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="3dec7-106">在代码中定义终结点通常是不可行的，因为已部署服务的绑定和地址通常与在部署服务时所用的绑定和地址不同。</span><span class="sxs-lookup"><span data-stu-id="3dec7-106">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="3dec7-107">一般说来，通过将绑定和寻址信息放置在代码之外，无需重新编译或重新部署应用程序即可更改这些信息。</span><span class="sxs-lookup"><span data-stu-id="3dec7-107">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="3dec7-108">可以使用执行所有以下配置步骤[配置编辑器工具 (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="3dec7-108">All of the following configuration steps can be undertaken using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="3dec7-109">此示例中的源副本，请参阅[BasicBinding](../../../docs/framework/wcf/samples/basicbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="3dec7-109">For the source copy of this example, see [BasicBinding](../../../docs/framework/wcf/samples/basicbinding.md).</span></span>  
  
### <a name="to-specify-the-basichttpbinding-to-use-to-configure-the-service"></a><span data-ttu-id="3dec7-110">指定要用于配置服务的 BasicHttpBinding</span><span class="sxs-lookup"><span data-stu-id="3dec7-110">To specify the BasicHttpBinding to use to configure the service</span></span>  
  
1.  <span data-ttu-id="3dec7-111">为该类型的服务定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="3dec7-111">Define a service contract for the type of service.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#1)]  
  
2.  <span data-ttu-id="3dec7-112">在服务类中实现该服务协定。</span><span class="sxs-lookup"><span data-stu-id="3dec7-112">Implement the service contract in a service class.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#2)]  
  
    > [!NOTE]
    >  <span data-ttu-id="3dec7-113">未在该服务的实现内部指定地址或绑定信息。</span><span class="sxs-lookup"><span data-stu-id="3dec7-113">Address or binding information is not specified inside the implementation of the service.</span></span> <span data-ttu-id="3dec7-114">而且，不必编写码就可以从配置文件中获取该信息。</span><span class="sxs-lookup"><span data-stu-id="3dec7-114">Also, code does not have to be written to fetch that information from the configuration file.</span></span>  
  
3.  <span data-ttu-id="3dec7-115">创建一个 Web.config 文件来配置使用 `CalculatorService` 的 <xref:System.ServiceModel.WSHttpBinding> 的终结点。</span><span class="sxs-lookup"><span data-stu-id="3dec7-115">Create a Web.config file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding>.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name=" CalculatorService" >  
            <endpoint   
            <-- Leave the address blank to be populated by default-->  
            <--from the hosting environment,in this case IIS, so -->  
            <-- the address will just be that of the IIS Virtual -->  
            <--Directory.-->  
                address=""   
            <--Specify the binding type -->  
                binding="wsHttpBinding"  
            <--Specify the binding configuration name for that -->  
            <--binding type. This is optional but useful if you  -->  
            <--want to modify the properties of the binding. -->  
            <--The bindingConfiguration name Binding1 is defined  -->  
            <--below in the bindings element.  -->  
                bindingConfiguration="Binding1"  
                contract="ICalculator" />  
          </service>  
        </services>  
        <bindings>  
          <wsHttpBinding>  
            <binding name="Binding1">  
              <-- Binding property values can be modified here. -->  
              <--See the next procedure. -->  
            </binding>  
          </wsHttpBinding>  
       </bindings>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
4.  <span data-ttu-id="3dec7-116">创建一个包含下行的 Service.svc 文件，然后将其放到 Internet 信息服务 (IIS) 虚拟目录中。</span><span class="sxs-lookup"><span data-stu-id="3dec7-116">Create a Service.svc file that contains the following line and place it in your Internet Information Services (IIS) virtual directory.</span></span>  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>   
    ```  
  
### <a name="to-modify-the-default-values-of-the-binding-properties"></a><span data-ttu-id="3dec7-117">修改绑定属性的默认值</span><span class="sxs-lookup"><span data-stu-id="3dec7-117">To modify the default values of the binding properties</span></span>  
  
1.  <span data-ttu-id="3dec7-118">若要修改的默认属性值之一<xref:System.ServiceModel.WSHttpBinding>，创建一个新的绑定配置名称- `<binding name="Binding1">` -内[ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)元素，并设置新的属性的值此绑定元素中的绑定。</span><span class="sxs-lookup"><span data-stu-id="3dec7-118">To modify one of the default property values of the <xref:System.ServiceModel.WSHttpBinding>, create a new binding configuration name - `<binding name="Binding1">` - within the [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element and set the new values for the attributes of the binding in this binding element.</span></span> <span data-ttu-id="3dec7-119">例如，若要将默认打开和关闭超时值从 1 分钟更改为 2 分钟，需要将下列内容添加到配置文件中。</span><span class="sxs-lookup"><span data-stu-id="3dec7-119">For example, to change the default open and close timeout values of 1 minute to 2 minutes, add the following to the configuration file.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
      <binding name="Binding1"  
               closeTimeout="00:02:00"  
               openTimeout="00:02:00">  
      </binding>  
    </wsHttpBinding>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3dec7-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3dec7-120">See Also</span></span>  
 [<span data-ttu-id="3dec7-121">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="3dec7-121">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="3dec7-122">指定终结点地址</span><span class="sxs-lookup"><span data-stu-id="3dec7-122">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)
