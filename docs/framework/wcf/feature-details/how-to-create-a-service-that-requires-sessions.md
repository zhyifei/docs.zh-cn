---
title: "如何：创建要求会话的服务"
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
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2e238598ccd33d9e6e77a2d09ea3b19fdefcefbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-service-that-requires-sessions"></a><span data-ttu-id="b70a1-102">如何：创建要求会话的服务</span><span class="sxs-lookup"><span data-stu-id="b70a1-102">How to: Create a Service That Requires Sessions</span></span>
<span data-ttu-id="b70a1-103">会话在两个或更多终结点之间创建一个共享状态，从而启用一些有用的功能，例如回调、多跳安全性以及客户端和服务实例之间的关联。</span><span class="sxs-lookup"><span data-stu-id="b70a1-103">Sessions create a shared state between two or more endpoints that enables useful features such as callbacks, multi-hop security, and associations between clients and service instances.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="b70a1-104">中的会话[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]应用程序，请参阅[使用会话](../../../../docs/framework/wcf/using-sessions.md)。</span><span class="sxs-lookup"><span data-stu-id="b70a1-104"> sessions in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] applications, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a><span data-ttu-id="b70a1-105">指定协定需要其绑定来支持会话</span><span class="sxs-lookup"><span data-stu-id="b70a1-105">To specify that a contract require its binding to support sessions</span></span>  
  
1.  <span data-ttu-id="b70a1-106">创建至少包含一个操作的服务协定。</span><span class="sxs-lookup"><span data-stu-id="b70a1-106">Create a service contract with at least one operation.</span></span> <span data-ttu-id="b70a1-107">有关如何创建服务协定的示例，请参阅[如何： 定义服务协定](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="b70a1-107">For an example of how to create a service contract, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span>  
  
2.  <span data-ttu-id="b70a1-108">修改声明协定的 <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>，将 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> 属性设置为：</span><span class="sxs-lookup"><span data-stu-id="b70a1-108">Modify the <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> that declares the contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> property to either:</span></span>  
  
    -   <span data-ttu-id="b70a1-109"><xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>（如果必须在会话中运行此协定）。</span><span class="sxs-lookup"><span data-stu-id="b70a1-109"><xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType> if this contract must be run within a session.</span></span>  
  
    -   <span data-ttu-id="b70a1-110"><xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType>（如果可以在会话中运行此协定）。</span><span class="sxs-lookup"><span data-stu-id="b70a1-110"><xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType> if this contract can be run within a session.</span></span>  
  
    -   <span data-ttu-id="b70a1-111"><xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType>（如果不得在会话中运行此协定）。</span><span class="sxs-lookup"><span data-stu-id="b70a1-111"><xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType> if this contract must not be run within a session.</span></span>  
  
3.  <span data-ttu-id="b70a1-112">配置服务终结点以使用支持会话的绑定。</span><span class="sxs-lookup"><span data-stu-id="b70a1-112">Configure your service endpoint to use a binding that supports sessions.</span></span> <span data-ttu-id="b70a1-113">下面的配置示例演示了支持 WS<xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>ReliableMessaging 会话的 `-` 的用法。</span><span class="sxs-lookup"><span data-stu-id="b70a1-113">The following configuration example shows the use of the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, which supports a WS`-`ReliableMessaging session.</span></span>  
  
     [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]   
  
## <a name="example"></a><span data-ttu-id="b70a1-114">示例</span><span class="sxs-lookup"><span data-stu-id="b70a1-114">Example</span></span>  
 <span data-ttu-id="b70a1-115">下面的示例代码演示如何指定协定级别会话要求并使用配置文件来支持 <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> 绑定的要求。</span><span class="sxs-lookup"><span data-stu-id="b70a1-115">The following example code shows how to specify a contract-level session requirement and use a configuration file to support that requirement with the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> binding.</span></span>  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)] 
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]      
 [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]     
  
## <a name="see-also"></a><span data-ttu-id="b70a1-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b70a1-116">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>  
 <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>
