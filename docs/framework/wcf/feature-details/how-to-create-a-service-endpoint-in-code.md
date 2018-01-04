---
title: "如何：在代码中创建服务终结点"
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
ms.assetid: 3fbb22fa-2930-48b8-b437-def1de87c6a0
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3de34d942c4c73e73f3cdb61ea2a0f6adea6e354
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-service-endpoint-in-code"></a><span data-ttu-id="ef17f-102">如何：在代码中创建服务终结点</span><span class="sxs-lookup"><span data-stu-id="ef17f-102">How to: Create a Service Endpoint in Code</span></span>
<span data-ttu-id="ef17f-103">在本示例中，将为计算器服务定义一个 `ICalculator` 协定，在 `CalculatorService` 类中实现该服务，然后在代码中定义其终结点（在这段代码中还指定该服务必须使用 <xref:System.ServiceModel.BasicHttpBinding> 类）。</span><span class="sxs-lookup"><span data-stu-id="ef17f-103">In this example, an `ICalculator` contract is defined for a calculator service, the service is implemented in the `CalculatorService` class, and then its endpoint is defined in code, where it is specified that the service must use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="ef17f-104">通常，最佳做法是以声明方式在配置中指定绑定和地址信息，而不是在代码中强制指定。</span><span class="sxs-lookup"><span data-stu-id="ef17f-104">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="ef17f-105">在代码中定义终结点通常是不可行的，因为已部署服务的绑定和地址通常与在部署服务时所用的绑定和地址不同。</span><span class="sxs-lookup"><span data-stu-id="ef17f-105">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="ef17f-106">一般说来，通过将绑定和寻址信息放置在代码之外，无需重新编译或重新部署应用程序即可更改这些信息。</span><span class="sxs-lookup"><span data-stu-id="ef17f-106">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
#### <a name="to-create-a-service-endpoint-in-code"></a><span data-ttu-id="ef17f-107">在代码中创建服务终结点</span><span class="sxs-lookup"><span data-stu-id="ef17f-107">To create a service endpoint in code</span></span>  
  
1.  <span data-ttu-id="ef17f-108">创建定义服务协定的接口。</span><span class="sxs-lookup"><span data-stu-id="ef17f-108">Create the interface that defines the service contract.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2.  <span data-ttu-id="ef17f-109">实现在步骤 1 中定义的服务协定。</span><span class="sxs-lookup"><span data-stu-id="ef17f-109">Implement the service contract defined in step 1.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3.  <span data-ttu-id="ef17f-110">在主机应用程序中，创建该服务的基址以及要用于该服务的绑定。</span><span class="sxs-lookup"><span data-stu-id="ef17f-110">In the hosting application, create the base address for the service and the binding to be used with the service.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4.  <span data-ttu-id="ef17f-111">创建宿主并调用 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29> 或其他重载之一来添加宿主的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="ef17f-111">Create the host and call <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29> or one of the other overloads to add the service endpoint for the host.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#6)]
     [!code-vb[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#6)]  
  
     <span data-ttu-id="ef17f-112">若要在代码中指定绑定，而不使用运行时提供的默认终结点，请在创建 <xref:System.ServiceModel.ServiceHost> 时将基址传递给构造函数，并且不调用 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>。</span><span class="sxs-lookup"><span data-stu-id="ef17f-112">To specify the binding in code, but to use the default endpoints provided by the runtime, pass the bass address into constructor when creating the <xref:System.ServiceModel.ServiceHost>, and do not call <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#7)]
     [!code-vb[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#7)]  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="ef17f-113">默认值为终结点，请参阅[简化配置](../../../../docs/framework/wcf/simplified-configuration.md)和[简化配置 WCF 服务](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ef17f-113"> default endpoints, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef17f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef17f-114">See Also</span></span>  
 [<span data-ttu-id="ef17f-115">如何：在代码中指定服务绑定</span><span class="sxs-lookup"><span data-stu-id="ef17f-115">How to: Specify a Service Binding in Code</span></span>](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md)
