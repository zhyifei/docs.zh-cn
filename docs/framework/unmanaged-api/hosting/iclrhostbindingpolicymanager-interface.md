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
ms.openlocfilehash: 9ed317a451e6e35aeac3bc1b83f78d1400ea5c07
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136439"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="b2311-102">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="b2311-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="b2311-103">为宿主提供方法，用于评估当前的绑定策略并传达指定程序集的策略更改。</span><span class="sxs-lookup"><span data-stu-id="b2311-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2311-104">方法</span><span class="sxs-lookup"><span data-stu-id="b2311-104">Methods</span></span>  
  
|<span data-ttu-id="b2311-105">方法</span><span class="sxs-lookup"><span data-stu-id="b2311-105">Method</span></span>|<span data-ttu-id="b2311-106">描述</span><span class="sxs-lookup"><span data-stu-id="b2311-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b2311-107">EvaluatePolicy 方法</span><span class="sxs-lookup"><span data-stu-id="b2311-107">EvaluatePolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="b2311-108">代表主机计算绑定策略。</span><span class="sxs-lookup"><span data-stu-id="b2311-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="b2311-109">ModifyApplicationPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="b2311-109">ModifyApplicationPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="b2311-110">修改指定程序集的绑定策略，并创建该策略的新版本。</span><span class="sxs-lookup"><span data-stu-id="b2311-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2311-111">要求</span><span class="sxs-lookup"><span data-stu-id="b2311-111">Requirements</span></span>  
 <span data-ttu-id="b2311-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2311-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2311-113">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b2311-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2311-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b2311-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2311-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2311-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2311-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2311-116">See also</span></span>

- [<span data-ttu-id="b2311-117">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="b2311-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="b2311-118">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="b2311-118">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="b2311-119">承载接口</span><span class="sxs-lookup"><span data-stu-id="b2311-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
