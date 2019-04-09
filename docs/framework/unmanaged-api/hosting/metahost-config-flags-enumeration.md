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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e322f5c7119d13c8a872bd87d00c1e55324b581
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135764"
---
# <a name="metahostconfigflags-enumeration"></a><span data-ttu-id="d2fd3-102">METAHOST_CONFIG_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="d2fd3-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="d2fd3-103">描述中返回的可能标志`pdwConfigFlags`的参数[iclrmetahostpolicy:: Getrequestedruntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)方法，指示是否存在并设置`useLegacyV2RuntimeActivationPolicy`属性中[ \<启动 > 元素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)的配置文件。</span><span class="sxs-lookup"><span data-stu-id="d2fd3-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2fd3-104">语法</span><span class="sxs-lookup"><span data-stu-id="d2fd3-104">Syntax</span></span>  
  
```  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="d2fd3-105">成员</span><span class="sxs-lookup"><span data-stu-id="d2fd3-105">Members</span></span>  
  
|<span data-ttu-id="d2fd3-106">成员</span><span class="sxs-lookup"><span data-stu-id="d2fd3-106">Member</span></span>|<span data-ttu-id="d2fd3-107">描述</span><span class="sxs-lookup"><span data-stu-id="d2fd3-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="d2fd3-108">`useLegacyV2RuntimeActivationPolicy`属性未出现在[\<启动 > 元素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)。</span><span class="sxs-lookup"><span data-stu-id="d2fd3-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="d2fd3-109">`useLegacyV2RuntimeActivationPolicy`属性已存在且设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="d2fd3-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="d2fd3-110">`useLegacyV2RuntimeActivationPolicy`属性已存在且设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="d2fd3-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="d2fd3-111">将此掩码应用于中返回的值`pdwConfigFlags`若要获取这些值与相关`useLegacyV2RuntimeActivationPolicy`。</span><span class="sxs-lookup"><span data-stu-id="d2fd3-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2fd3-112">备注</span><span class="sxs-lookup"><span data-stu-id="d2fd3-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2fd3-113">要求</span><span class="sxs-lookup"><span data-stu-id="d2fd3-113">Requirements</span></span>  
 <span data-ttu-id="d2fd3-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d2fd3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2fd3-115">**标头：** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="d2fd3-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="d2fd3-116">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d2fd3-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d2fd3-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="d2fd3-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d2fd3-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2fd3-118">See also</span></span>

- [<span data-ttu-id="d2fd3-119">承载枚举</span><span class="sxs-lookup"><span data-stu-id="d2fd3-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="d2fd3-120">GetRequestedRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="d2fd3-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="d2fd3-121">\<启动 > 元素</span><span class="sxs-lookup"><span data-stu-id="d2fd3-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
