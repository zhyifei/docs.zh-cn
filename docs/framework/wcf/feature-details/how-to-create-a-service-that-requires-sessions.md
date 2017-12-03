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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f9cff53b598d4e477488bcb5b5e87be62e78bb9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-service-that-requires-sessions"></a>如何：创建要求会话的服务
会话在两个或更多终结点之间创建一个共享状态，从而启用一些有用的功能，例如回调、多跳安全性以及客户端和服务实例之间的关联。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]中的会话[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]应用程序，请参阅[使用会话](../../../../docs/framework/wcf/using-sessions.md)。  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a>指定协定需要其绑定来支持会话  
  
1.  创建至少包含一个操作的服务协定。 有关如何创建服务协定的示例，请参阅[如何： 定义服务协定](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)。  
  
2.  修改声明协定的 <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>，将 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> 属性设置为：  
  
    -   <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>（如果必须在会话中运行此协定）。  
  
    -   <xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType>（如果可以在会话中运行此协定）。  
  
    -   <xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType>（如果不得在会话中运行此协定）。  
  
3.  配置服务终结点以使用支持会话的绑定。 下面的配置示例演示了支持 WS<xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>ReliableMessaging 会话的 `-` 的用法。  
  
     [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]   
  
## <a name="example"></a>示例  
 下面的示例代码演示如何指定协定级别会话要求并使用配置文件来支持 <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> 绑定的要求。  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)] 
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]      
 [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]     
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>  
 <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>
