---
title: 服务：Security Calls Not Authorized（未授权的安全调用次数）
ms.date: 03/30/2017
ms.assetid: 3024b20a-5250-4bd1-a38c-c6d79f89610b
ms.openlocfilehash: a38b5e0eb467a5cad698fd6e3e01c0adef825d2f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773311"
---
# <a name="service-security-calls-not-authorized"></a><span data-ttu-id="66618-102">服务：Security Calls Not Authorized（未授权的安全调用次数）</span><span class="sxs-lookup"><span data-stu-id="66618-102">Service: Security Calls Not Authorized</span></span>
<span data-ttu-id="66618-103">计数器名称：未授权的安全调用。</span><span class="sxs-lookup"><span data-stu-id="66618-103">Counter Name: Security Calls Not Authorized.</span></span>  
  
## <a name="description"></a><span data-ttu-id="66618-104">描述</span><span class="sxs-lookup"><span data-stu-id="66618-104">Description</span></span>  
 <span data-ttu-id="66618-105">当 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 方法返回 `false` 时，此计数器将递增。</span><span class="sxs-lookup"><span data-stu-id="66618-105">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="66618-106">它指示传入的消息来自有效的用户并得到了良好保护，但该用户没有获得执行特定任务的授权。</span><span class="sxs-lookup"><span data-stu-id="66618-106">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>
