---
title: Security Calls Not Authorized（未授权的安全调用次数）
ms.date: 03/30/2017
ms.assetid: cb6acdcd-7336-42e1-9ae8-ac891336cd58
author: BrucePerlerMS
ms.openlocfilehash: 6af1c7576e6a0fe7ae21f6f1997b2ebe3b919214
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47111901"
---
# <a name="security-calls-not-authorized"></a><span data-ttu-id="b2ada-102">Security Calls Not Authorized（未授权的安全调用次数）</span><span class="sxs-lookup"><span data-stu-id="b2ada-102">Security Calls Not Authorized</span></span>
<span data-ttu-id="b2ada-103">计数器名称：Security Calls Not Authorized（未授权的安全调用次数）。</span><span class="sxs-lookup"><span data-stu-id="b2ada-103">Counter Name: Security Calls Not Authorized.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b2ada-104">描述</span><span class="sxs-lookup"><span data-stu-id="b2ada-104">Description</span></span>  
 <span data-ttu-id="b2ada-105">当 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 方法返回 `false` 时，此计数器将递增。</span><span class="sxs-lookup"><span data-stu-id="b2ada-105">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="b2ada-106">它指示传入的消息来自有效的用户并得到了良好保护，但该用户没有获得执行特定任务的授权。</span><span class="sxs-lookup"><span data-stu-id="b2ada-106">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>
