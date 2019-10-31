---
title: METAHOST_CONFIG_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- METAHOST_CONFIG_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_CONFIG_FLAGS
helpviewer_keywords:
- METAHOST_CONFIG_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 6f1e389f-ed99-4d6a-a0ba-72d7d869a01d
topic_type:
- apiref
ms.openlocfilehash: 07cab119810c4da25d16a4ad7c13f2d2bda16455
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140307"
---
# <a name="metahost_config_flags-enumeration"></a><span data-ttu-id="77983-102">METAHOST_CONFIG_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="77983-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="77983-103">描述在[ICLRMetaHostPolicy：： GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)方法的 `pdwConfigFlags` 参数中返回的可能标志，指示[\<启动 > 元素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)中的 `useLegacyV2RuntimeActivationPolicy` 特性的状态和设置配置文件。</span><span class="sxs-lookup"><span data-stu-id="77983-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77983-104">语法</span><span class="sxs-lookup"><span data-stu-id="77983-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="77983-105">Members</span><span class="sxs-lookup"><span data-stu-id="77983-105">Members</span></span>  
  
|<span data-ttu-id="77983-106">成员</span><span class="sxs-lookup"><span data-stu-id="77983-106">Member</span></span>|<span data-ttu-id="77983-107">描述</span><span class="sxs-lookup"><span data-stu-id="77983-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="77983-108">[\<startup > 元素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)中不存在 `useLegacyV2RuntimeActivationPolicy` 特性。</span><span class="sxs-lookup"><span data-stu-id="77983-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="77983-109">`useLegacyV2RuntimeActivationPolicy` 属性存在并设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="77983-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="77983-110">`useLegacyV2RuntimeActivationPolicy` 属性存在并设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="77983-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="77983-111">将此掩码应用到 `pdwConfigFlags` 中返回的值，以获取与 `useLegacyV2RuntimeActivationPolicy`相关的值。</span><span class="sxs-lookup"><span data-stu-id="77983-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77983-112">备注</span><span class="sxs-lookup"><span data-stu-id="77983-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77983-113">要求</span><span class="sxs-lookup"><span data-stu-id="77983-113">Requirements</span></span>  
 <span data-ttu-id="77983-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="77983-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77983-115">**标头：** Metahost</span><span class="sxs-lookup"><span data-stu-id="77983-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="77983-116">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="77983-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77983-117">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77983-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77983-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="77983-118">See also</span></span>

- [<span data-ttu-id="77983-119">承载枚举</span><span class="sxs-lookup"><span data-stu-id="77983-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="77983-120">GetRequestedRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="77983-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="77983-121">\<startup> 元素</span><span class="sxs-lookup"><span data-stu-id="77983-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
