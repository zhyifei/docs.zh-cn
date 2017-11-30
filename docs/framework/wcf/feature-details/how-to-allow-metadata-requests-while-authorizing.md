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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 103aba5118810064c1cafb7c82634ef000ced667
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a><span data-ttu-id="58db7-102">如何：授权时允许元数据请求</span><span class="sxs-lookup"><span data-stu-id="58db7-102">How To: Allow Metadata Requests While Authorizing</span></span>
<span data-ttu-id="58db7-103">自定义授权时，可能有必要允许处理对元数据的请求。</span><span class="sxs-lookup"><span data-stu-id="58db7-103">During custom authorization, it may be necessary to allow a request for metadata to be processed.</span></span> <span data-ttu-id="58db7-104">以下主题将演练验证此类请求的步骤。</span><span class="sxs-lookup"><span data-stu-id="58db7-104">The following topic walks through the steps to validate such a request.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="58db7-105">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]授权，请参阅[授权](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)。</span><span class="sxs-lookup"><span data-stu-id="58db7-105"> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] authorization, see [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
### <a name="to-allow-metadata-requests-during-authorization"></a><span data-ttu-id="58db7-106">授权时允许元数据请求</span><span class="sxs-lookup"><span data-stu-id="58db7-106">To allow metadata requests during authorization</span></span>  
  
1.  <span data-ttu-id="58db7-107">创建 <xref:System.ServiceModel.ServiceAuthorizationManager> 类的扩展。</span><span class="sxs-lookup"><span data-stu-id="58db7-107">Create an extension of the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>  
  
2.  <span data-ttu-id="58db7-108">重写 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="58db7-108">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="58db7-109">取决于是否允许授权，该方法返回 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="58db7-109">The method returns `true` or `false` depending on whether authorization is allowed.</span></span> <span data-ttu-id="58db7-110">有关当前过程的信息，请参见作为参数传递给该方法的 <xref:System.ServiceModel.OperationContext>。</span><span class="sxs-lookup"><span data-stu-id="58db7-110">Information about the current procedure is found in the <xref:System.ServiceModel.OperationContext> passed as a parameter to the method.</span></span>  
  
3.  <span data-ttu-id="58db7-111">重写时，检查协定名称、命名空间和操作，如在以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="58db7-111">In the override, check the contract name, namespace, and the action as shown in the following example.</span></span> <span data-ttu-id="58db7-112">如果条件无效，则将返回 `true.`。</span><span class="sxs-lookup"><span data-stu-id="58db7-112">If the conditions are valid, then return `true.`</span></span>  
  
4.  <span data-ttu-id="58db7-113">使用扩展点利用类。</span><span class="sxs-lookup"><span data-stu-id="58db7-113">Use the extensibility point to employ the class.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="58db7-114">[如何： 创建自定义授权管理器服务](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)。</span><span class="sxs-lookup"><span data-stu-id="58db7-114"> [How to: Create a Custom Authorization Manager for a Service](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="58db7-115">示例</span><span class="sxs-lookup"><span data-stu-id="58db7-115">Example</span></span>  
 <span data-ttu-id="58db7-116">下面的示例演示对 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 方法的重写。</span><span class="sxs-lookup"><span data-stu-id="58db7-116">The following example shows an override of the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span>  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="58db7-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58db7-117">See Also</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [<span data-ttu-id="58db7-118">授权</span><span class="sxs-lookup"><span data-stu-id="58db7-118">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [<span data-ttu-id="58db7-119">管理声明和使用标识模型的授权</span><span class="sxs-lookup"><span data-stu-id="58db7-119">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
