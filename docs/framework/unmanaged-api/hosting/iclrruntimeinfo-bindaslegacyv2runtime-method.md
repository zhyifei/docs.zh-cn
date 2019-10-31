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
ms.openlocfilehash: d37ec8e17e62f58212a5f79f4d6b6aa75f57bf7c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120260"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="40598-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime 方法</span><span class="sxs-lookup"><span data-stu-id="40598-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="40598-103">绑定所有旧公共语言运行时（CLR）版本2激活策略决策的当前运行时。</span><span class="sxs-lookup"><span data-stu-id="40598-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40598-104">语法</span><span class="sxs-lookup"><span data-stu-id="40598-104">Syntax</span></span>  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="40598-105">返回值</span><span class="sxs-lookup"><span data-stu-id="40598-105">Return Value</span></span>  
 <span data-ttu-id="40598-106">此方法返回以下特定 Hresult：</span><span class="sxs-lookup"><span data-stu-id="40598-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="40598-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40598-107">HRESULT</span></span>|<span data-ttu-id="40598-108">描述</span><span class="sxs-lookup"><span data-stu-id="40598-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40598-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="40598-109">S_OK</span></span>|<span data-ttu-id="40598-110">绑定成功，或已将此运行时绑定为旧版 CLR 版本2激活策略运行时。</span><span class="sxs-lookup"><span data-stu-id="40598-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="40598-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="40598-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="40598-112">已将其他运行时绑定到旧版 CLR 版本2激活策略。</span><span class="sxs-lookup"><span data-stu-id="40598-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40598-113">备注</span><span class="sxs-lookup"><span data-stu-id="40598-113">Remarks</span></span>  
 <span data-ttu-id="40598-114">如果当前运行时已绑定到所有旧 CLR 版本2激活策略决策（例如，通过使用配置文件中[\<startup > 元素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)上的 `useLegacyV2RuntimeActivationPolicy` 属性），则此方法不会返回错误结果;相反，结果是 S_OK，就如同方法成功绑定了旧激活策略一样。</span><span class="sxs-lookup"><span data-stu-id="40598-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40598-115">要求</span><span class="sxs-lookup"><span data-stu-id="40598-115">Requirements</span></span>  
 <span data-ttu-id="40598-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40598-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40598-117">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="40598-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="40598-118">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="40598-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40598-119">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40598-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40598-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="40598-120">See also</span></span>

- [<span data-ttu-id="40598-121">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="40598-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="40598-122">承载接口</span><span class="sxs-lookup"><span data-stu-id="40598-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="40598-123">承载</span><span class="sxs-lookup"><span data-stu-id="40598-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="40598-124">\<startup> 元素</span><span class="sxs-lookup"><span data-stu-id="40598-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
