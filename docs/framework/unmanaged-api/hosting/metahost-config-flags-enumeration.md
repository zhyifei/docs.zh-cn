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
ms.openlocfilehash: a13897f71bb675b982a84d57d310b799989c41aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442925"
---
# <a name="metahostconfigflags-enumeration"></a><span data-ttu-id="8f565-102">METAHOST_CONFIG_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="8f565-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="8f565-103">描述中返回的可能标志`pdwConfigFlags`参数[iclrmetahostpolicy:: Getrequestedruntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)方法，指示存在并设置`useLegacyV2RuntimeActivationPolicy`属性中[ \<启动 > 元素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)的配置文件。</span><span class="sxs-lookup"><span data-stu-id="8f565-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f565-104">语法</span><span class="sxs-lookup"><span data-stu-id="8f565-104">Syntax</span></span>  
  
```  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="8f565-105">成员</span><span class="sxs-lookup"><span data-stu-id="8f565-105">Members</span></span>  
  
|<span data-ttu-id="8f565-106">成员</span><span class="sxs-lookup"><span data-stu-id="8f565-106">Member</span></span>|<span data-ttu-id="8f565-107">描述</span><span class="sxs-lookup"><span data-stu-id="8f565-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="8f565-108">`useLegacyV2RuntimeActivationPolicy`属性未出现在[\<启动 > 元素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)。</span><span class="sxs-lookup"><span data-stu-id="8f565-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="8f565-109">`useLegacyV2RuntimeActivationPolicy`属性已存在，并且已设置到`true`。</span><span class="sxs-lookup"><span data-stu-id="8f565-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="8f565-110">`useLegacyV2RuntimeActivationPolicy`属性已存在，并且已设置到`false`。</span><span class="sxs-lookup"><span data-stu-id="8f565-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="8f565-111">将此掩码应用于返回的值`pdwConfigFlags`若要获取的值与相关`useLegacyV2RuntimeActivationPolicy`。</span><span class="sxs-lookup"><span data-stu-id="8f565-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f565-112">备注</span><span class="sxs-lookup"><span data-stu-id="8f565-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f565-113">要求</span><span class="sxs-lookup"><span data-stu-id="8f565-113">Requirements</span></span>  
 <span data-ttu-id="8f565-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f565-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f565-115">**标头：** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="8f565-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="8f565-116">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8f565-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f565-117">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f565-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f565-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f565-118">See Also</span></span>  
 [<span data-ttu-id="8f565-119">承载枚举</span><span class="sxs-lookup"><span data-stu-id="8f565-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [<span data-ttu-id="8f565-120">GetRequestedRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="8f565-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)  
 [<span data-ttu-id="8f565-121">\<startup> 元素</span><span class="sxs-lookup"><span data-stu-id="8f565-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
