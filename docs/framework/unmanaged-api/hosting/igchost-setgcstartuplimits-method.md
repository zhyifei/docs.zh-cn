---
title: IGCHost::SetGCStartupLimits 方法
ms.date: 03/30/2017
api_name:
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 365261883f0b81884bb7cf70614628c05f9067c5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221002"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="6ea78-102">IGCHost::SetGCStartupLimits 方法</span><span class="sxs-lookup"><span data-stu-id="6ea78-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="6ea78-103">设置第 0 代段大小和最大大小。</span><span class="sxs-lookup"><span data-stu-id="6ea78-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6ea78-104">从开始[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]，可以设置段大小和最大第 0 代大小值大于`DWORD`通过使用[IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6ea78-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea78-105">语法</span><span class="sxs-lookup"><span data-stu-id="6ea78-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ea78-106">参数</span><span class="sxs-lookup"><span data-stu-id="6ea78-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="6ea78-107">[in]由垃圾回收系统段的大小。</span><span class="sxs-lookup"><span data-stu-id="6ea78-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="6ea78-108">[in]第 0 代最大大小。</span><span class="sxs-lookup"><span data-stu-id="6ea78-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ea78-109">备注</span><span class="sxs-lookup"><span data-stu-id="6ea78-109">Remarks</span></span>  
 <span data-ttu-id="6ea78-110">`SetGCStartupLimits`可能只有一次调用方法。</span><span class="sxs-lookup"><span data-stu-id="6ea78-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="6ea78-111">以后无法更改这些值。</span><span class="sxs-lookup"><span data-stu-id="6ea78-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ea78-112">要求</span><span class="sxs-lookup"><span data-stu-id="6ea78-112">Requirements</span></span>  
 <span data-ttu-id="6ea78-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6ea78-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ea78-114">**标头：** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="6ea78-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="6ea78-115">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6ea78-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6ea78-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="6ea78-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6ea78-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ea78-117">See also</span></span>

- [<span data-ttu-id="6ea78-118">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="6ea78-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
