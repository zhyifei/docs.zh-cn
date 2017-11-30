---
title: "EBindPolicyLevels 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EBindPolicyLevels
api_location: mscoree.dll
api_type: COM
f1_keywords: EBindPolicyLevels
helpviewer_keywords: EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e55fdb58129cd530bb63f26fab0be471b133d62f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="42e95-102">EBindPolicyLevels 枚举</span><span class="sxs-lookup"><span data-stu-id="42e95-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="42e95-103">提供一些标志以指定在哪个应用或修改的程序集策略级别。</span><span class="sxs-lookup"><span data-stu-id="42e95-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42e95-104">语法</span><span class="sxs-lookup"><span data-stu-id="42e95-104">Syntax</span></span>  
  
```  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a><span data-ttu-id="42e95-105">成员</span><span class="sxs-lookup"><span data-stu-id="42e95-105">Members</span></span>  
  
|<span data-ttu-id="42e95-106">成员</span><span class="sxs-lookup"><span data-stu-id="42e95-106">Member</span></span>|<span data-ttu-id="42e95-107">描述</span><span class="sxs-lookup"><span data-stu-id="42e95-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="42e95-108">指定应在管理员级别应用策略。</span><span class="sxs-lookup"><span data-stu-id="42e95-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="42e95-109">指定应在应用程序级别应用策略。</span><span class="sxs-lookup"><span data-stu-id="42e95-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="42e95-110">指定应在主机级别上应用策略。</span><span class="sxs-lookup"><span data-stu-id="42e95-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="42e95-111">不指定任何策略级别标志。</span><span class="sxs-lookup"><span data-stu-id="42e95-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="42e95-112">指定应在发布服务器级别应用策略。</span><span class="sxs-lookup"><span data-stu-id="42e95-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="42e95-113">指定策略应适用变量级别。</span><span class="sxs-lookup"><span data-stu-id="42e95-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="42e95-114">指定策略应支持的.NET Framework 程序集的实现之间的可移植性。</span><span class="sxs-lookup"><span data-stu-id="42e95-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="42e95-115">请参阅[ \<supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md)配置文件元素。</span><span class="sxs-lookup"><span data-stu-id="42e95-115">See the [\<supportPortability>](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="42e95-116">指定策略应统一到的公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="42e95-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42e95-117">备注</span><span class="sxs-lookup"><span data-stu-id="42e95-117">Remarks</span></span>  
 <span data-ttu-id="42e95-118">此枚举传递给方法的[ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)接口来在应用程序策略中指定的更改。</span><span class="sxs-lookup"><span data-stu-id="42e95-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42e95-119">要求</span><span class="sxs-lookup"><span data-stu-id="42e95-119">Requirements</span></span>  
 <span data-ttu-id="42e95-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="42e95-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42e95-121">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="42e95-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42e95-122">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="42e95-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42e95-123">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42e95-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42e95-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42e95-124">See Also</span></span>  
 [<span data-ttu-id="42e95-125">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="42e95-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="42e95-126">承载枚举</span><span class="sxs-lookup"><span data-stu-id="42e95-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
