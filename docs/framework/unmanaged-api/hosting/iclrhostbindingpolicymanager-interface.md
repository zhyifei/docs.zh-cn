---
title: ICLRHostBindingPolicyManager 接口
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e494bbbd08a77329b7b64816216e4bb2e1b724a2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074191"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="d111d-102">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="d111d-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="d111d-103">提供用于主机来评估当前的绑定策略和通信策略更改指定的程序集的方法。</span><span class="sxs-lookup"><span data-stu-id="d111d-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d111d-104">方法</span><span class="sxs-lookup"><span data-stu-id="d111d-104">Methods</span></span>  
  
|<span data-ttu-id="d111d-105">方法</span><span class="sxs-lookup"><span data-stu-id="d111d-105">Method</span></span>|<span data-ttu-id="d111d-106">描述</span><span class="sxs-lookup"><span data-stu-id="d111d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d111d-107">EvaluatePolicy 方法</span><span class="sxs-lookup"><span data-stu-id="d111d-107">EvaluatePolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="d111d-108">代表主机的计算结果绑定策略。</span><span class="sxs-lookup"><span data-stu-id="d111d-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="d111d-109">ModifyApplicationPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="d111d-109">ModifyApplicationPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="d111d-110">修改为指定的程序集绑定策略和创建策略的新版本。</span><span class="sxs-lookup"><span data-stu-id="d111d-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d111d-111">要求</span><span class="sxs-lookup"><span data-stu-id="d111d-111">Requirements</span></span>  
 <span data-ttu-id="d111d-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d111d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d111d-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d111d-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d111d-114">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d111d-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d111d-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="d111d-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d111d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d111d-116">See also</span></span>

- [<span data-ttu-id="d111d-117">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="d111d-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="d111d-118">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="d111d-118">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="d111d-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="d111d-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
