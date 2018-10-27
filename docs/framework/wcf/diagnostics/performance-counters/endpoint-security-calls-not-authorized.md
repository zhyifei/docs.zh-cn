---
title: 终结点：未授权的安全调用次数
ms.date: 03/30/2017
ms.assetid: d25095ff-9ff0-4c69-a674-4e6a9fe3f4dc
ms.openlocfilehash: b37d4cd33c41c6e978dd82ca7ce6332302a843de
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2018
ms.locfileid: "50046664"
---
# <a name="endpoint-security-calls-not-authorized"></a><span data-ttu-id="1e8e2-102">终结点：未授权的安全调用次数</span><span class="sxs-lookup"><span data-stu-id="1e8e2-102">Endpoint: Security Calls Not Authorized</span></span>
<span data-ttu-id="1e8e2-103">计数器名称：Security Calls Not Authorized（未授权的安全调用次数）。</span><span class="sxs-lookup"><span data-stu-id="1e8e2-103">Counter Name: Security Calls Not Authorized.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1e8e2-104">描述</span><span class="sxs-lookup"><span data-stu-id="1e8e2-104">Description</span></span>  
 <span data-ttu-id="1e8e2-105">当 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 方法返回 `false` 时，此计数器将递增。</span><span class="sxs-lookup"><span data-stu-id="1e8e2-105">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="1e8e2-106">它指示传入的消息来自有效的用户并得到了良好保护，但该用户没有获得执行特定任务的授权。</span><span class="sxs-lookup"><span data-stu-id="1e8e2-106">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>
