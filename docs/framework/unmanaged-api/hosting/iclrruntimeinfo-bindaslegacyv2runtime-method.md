---
title: "ICLRRuntimeInfo::BindAsLegacyV2Runtime 方法"
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
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5552214f722cd7f9a56c2fce1e7c67de41d5bb1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="3a931-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime 方法</span><span class="sxs-lookup"><span data-stu-id="3a931-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="3a931-103">将绑定所有旧公共语言运行时 (CLR) 版本 2 激活策略决策的当前运行时。</span><span class="sxs-lookup"><span data-stu-id="3a931-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a931-104">语法</span><span class="sxs-lookup"><span data-stu-id="3a931-104">Syntax</span></span>  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3a931-105">返回值</span><span class="sxs-lookup"><span data-stu-id="3a931-105">Return Value</span></span>  
 <span data-ttu-id="3a931-106">此方法返回以下特定 Hresult:</span><span class="sxs-lookup"><span data-stu-id="3a931-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="3a931-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3a931-107">HRESULT</span></span>|<span data-ttu-id="3a931-108">描述</span><span class="sxs-lookup"><span data-stu-id="3a931-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a931-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="3a931-109">S_OK</span></span>|<span data-ttu-id="3a931-110">绑定成功，或此运行时已被绑定为旧 CLR 版本 2 激活策略运行时。</span><span class="sxs-lookup"><span data-stu-id="3a931-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="3a931-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="3a931-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="3a931-112">不同的运行时已绑定到的旧的 CLR 版本 2 激活策略。</span><span class="sxs-lookup"><span data-stu-id="3a931-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a931-113">备注</span><span class="sxs-lookup"><span data-stu-id="3a931-113">Remarks</span></span>  
 <span data-ttu-id="3a931-114">如果当前的运行时已为所有旧式 CLR 版本 2 激活策略决策绑定 (例如，通过使用`useLegacyV2RuntimeActivationPolicy`属性[\<启动 > 元素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)配置文件中)，此方法不返回错误结果;相反，结果是，则为 S_OK，就像它是该方法已成功绑定旧式激活策略。</span><span class="sxs-lookup"><span data-stu-id="3a931-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a931-115">惠?</span><span class="sxs-lookup"><span data-stu-id="3a931-115">Requirements</span></span>  
 <span data-ttu-id="3a931-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3a931-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a931-117">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3a931-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3a931-118">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3a931-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a931-119">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a931-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a931-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a931-120">See Also</span></span>  
 [<span data-ttu-id="3a931-121">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="3a931-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="3a931-122">承载接口</span><span class="sxs-lookup"><span data-stu-id="3a931-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="3a931-123">承载</span><span class="sxs-lookup"><span data-stu-id="3a931-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="3a931-124">\<启动 > 元素</span><span class="sxs-lookup"><span data-stu-id="3a931-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
