---
title: "如何：授权时允许元数据请求"
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
helpviewer_keywords: allowing metadata requests while authorizing [WCF]
ms.assetid: 90cec34f-b619-452b-a056-8b1c0de49d05
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b388a7517dbab8d30df51bfffac0058ded04bda
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a>如何：授权时允许元数据请求
自定义授权时，可能有必要允许处理对元数据的请求。 以下主题将演练验证此类请求的步骤。  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]授权，请参阅[授权](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)。  
  
### <a name="to-allow-metadata-requests-during-authorization"></a>授权时允许元数据请求  
  
1.  创建 <xref:System.ServiceModel.ServiceAuthorizationManager> 类的扩展。  
  
2.  重写 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 方法。 取决于是否允许授权，该方法返回 `true` 或 `false`。 有关当前过程的信息，请参见作为参数传递给该方法的 <xref:System.ServiceModel.OperationContext>。  
  
3.  重写时，检查协定名称、命名空间和操作，如在以下示例所示。 如果条件无效，则将返回 `true.`。  
  
4.  使用扩展点利用类。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][如何： 创建自定义授权管理器服务](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示对 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 方法的重写。  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [授权](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [管理声明和使用标识模型的授权](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
