---
title: "在 ClaimSet 中查找声明"
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
helpviewer_keywords:
- claims [WCF], finding in a claimset
- claims [WCF]
ms.assetid: a76ce107-aeb3-47d0-bfa9-134c53664e20
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cc6a4d98529357aa58f55be2fc33d6b7a95a8999
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="finding-claims-in-a-claimset"></a><span data-ttu-id="eaa46-102">在 ClaimSet 中查找声明</span><span class="sxs-lookup"><span data-stu-id="eaa46-102">Finding Claims in a ClaimSet</span></span>
<span data-ttu-id="eaa46-103">在使用基于声明的授权时，一项常见任务就是检查 <xref:System.IdentityModel.Claims.ClaimSet> 的内容以查找特定类型的声明。</span><span class="sxs-lookup"><span data-stu-id="eaa46-103">Examining the content of a <xref:System.IdentityModel.Claims.ClaimSet> for particular types of claims is a common task when using claim-based authorization.</span></span> <span data-ttu-id="eaa46-104">若要检查 <xref:System.IdentityModel.Claims.ClaimSet> 以查找是否存在特定声明，请使用 <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="eaa46-104">To examine a <xref:System.IdentityModel.Claims.ClaimSet> for the presence of particular claims, use the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> method.</span></span> <span data-ttu-id="eaa46-105">相对于直接在 <xref:System.IdentityModel.Claims.ClaimSet> 上循环，该方法可以提供更好的性能。</span><span class="sxs-lookup"><span data-stu-id="eaa46-105">This method provides better performance than iterating directly over the <xref:System.IdentityModel.Claims.ClaimSet>.</span></span> <span data-ttu-id="eaa46-106">下面的示例演示此用法。</span><span class="sxs-lookup"><span data-stu-id="eaa46-106">The following example demonstrates this usage.</span></span> <span data-ttu-id="eaa46-107">请注意，`claimType` 和 `claimRight` 参数可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="eaa46-107">Note that the `claimType` and `claimRight` parameters can be `null`.</span></span> <span data-ttu-id="eaa46-108">在此例中，这些参数将与所有声明类型以及声明权限相匹配。</span><span class="sxs-lookup"><span data-stu-id="eaa46-108">In that case, the parameters will match all claim types and claim rights.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eaa46-109">示例</span><span class="sxs-lookup"><span data-stu-id="eaa46-109">Example</span></span>  
 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="eaa46-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eaa46-110">See Also</span></span>  
 [<span data-ttu-id="eaa46-111">管理声明和使用标识模型的授权</span><span class="sxs-lookup"><span data-stu-id="eaa46-111">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
