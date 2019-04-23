---
title: ICLRRuntimeInfo::BindAsLegacyV2Runtime 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 647c87b6f42b01922a385d502d72410af3140cd2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59095342"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="3c05c-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime 方法</span><span class="sxs-lookup"><span data-stu-id="3c05c-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="3c05c-103">将绑定所有旧版公共语言运行时 (CLR) 版本 2 激活策略决策的当前运行时。</span><span class="sxs-lookup"><span data-stu-id="3c05c-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c05c-104">语法</span><span class="sxs-lookup"><span data-stu-id="3c05c-104">Syntax</span></span>  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3c05c-105">返回值</span><span class="sxs-lookup"><span data-stu-id="3c05c-105">Return Value</span></span>  
 <span data-ttu-id="3c05c-106">此方法将返回以下特定的 Hresult:</span><span class="sxs-lookup"><span data-stu-id="3c05c-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="3c05c-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c05c-107">HRESULT</span></span>|<span data-ttu-id="3c05c-108">描述</span><span class="sxs-lookup"><span data-stu-id="3c05c-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c05c-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="3c05c-109">S_OK</span></span>|<span data-ttu-id="3c05c-110">绑定成功，或此运行时已被绑定为旧 CLR 版本 2 激活策略运行时。</span><span class="sxs-lookup"><span data-stu-id="3c05c-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="3c05c-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="3c05c-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="3c05c-112">不同的运行时已绑定到旧的 CLR 版本 2 激活策略。</span><span class="sxs-lookup"><span data-stu-id="3c05c-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c05c-113">备注</span><span class="sxs-lookup"><span data-stu-id="3c05c-113">Remarks</span></span>  
 <span data-ttu-id="3c05c-114">如果当前运行时已绑定的所有旧 CLR 版本 2 激活策略决策 (例如，通过使用`useLegacyV2RuntimeActivationPolicy`特性，可以在[\<启动 > 元素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)配置文件中)，此方法不会返回错误结果;相反，则结果为 S_OK，只是因为它将该方法已成功绑定旧式激活策略。</span><span class="sxs-lookup"><span data-stu-id="3c05c-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c05c-115">要求</span><span class="sxs-lookup"><span data-stu-id="3c05c-115">Requirements</span></span>  
 <span data-ttu-id="3c05c-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3c05c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c05c-117">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3c05c-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3c05c-118">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3c05c-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c05c-119">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c05c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c05c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c05c-120">See also</span></span>

- [<span data-ttu-id="3c05c-121">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="3c05c-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="3c05c-122">承载接口</span><span class="sxs-lookup"><span data-stu-id="3c05c-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="3c05c-123">承载</span><span class="sxs-lookup"><span data-stu-id="3c05c-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="3c05c-124">\<startup> 元素</span><span class="sxs-lookup"><span data-stu-id="3c05c-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
