---
title: "ICLRHostBindingPolicyManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2dd55268e9f54554ec3e9a9b61573b708aa5acc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="2f0d8-102">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="2f0d8-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="2f0d8-103">提供用于宿主评估当前的绑定策略和通信策略更改指定的程序集的方法。</span><span class="sxs-lookup"><span data-stu-id="2f0d8-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2f0d8-104">方法</span><span class="sxs-lookup"><span data-stu-id="2f0d8-104">Methods</span></span>  
  
|<span data-ttu-id="2f0d8-105">方法</span><span class="sxs-lookup"><span data-stu-id="2f0d8-105">Method</span></span>|<span data-ttu-id="2f0d8-106">描述</span><span class="sxs-lookup"><span data-stu-id="2f0d8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2f0d8-107">EvaluatePolicy 方法</span><span class="sxs-lookup"><span data-stu-id="2f0d8-107">EvaluatePolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="2f0d8-108">代表主机的计算结果绑定策略。</span><span class="sxs-lookup"><span data-stu-id="2f0d8-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="2f0d8-109">ModifyApplicationPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="2f0d8-109">ModifyApplicationPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="2f0d8-110">修改指定的程序集绑定策略，并创建新版本的策略。</span><span class="sxs-lookup"><span data-stu-id="2f0d8-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2f0d8-111">惠?</span><span class="sxs-lookup"><span data-stu-id="2f0d8-111">Requirements</span></span>  
 <span data-ttu-id="2f0d8-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2f0d8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f0d8-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2f0d8-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2f0d8-114">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2f0d8-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f0d8-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f0d8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f0d8-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f0d8-116">See Also</span></span>  
 [<span data-ttu-id="2f0d8-117">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="2f0d8-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="2f0d8-118">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="2f0d8-118">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="2f0d8-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="2f0d8-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
