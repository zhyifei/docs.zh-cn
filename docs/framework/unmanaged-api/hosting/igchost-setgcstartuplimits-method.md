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
ms.openlocfilehash: cbe94aa67c9cf9ac587b7fca9f5cbeca4870506b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437204"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="249ce-102">IGCHost::SetGCStartupLimits 方法</span><span class="sxs-lookup"><span data-stu-id="249ce-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="249ce-103">为第 0 代中设置的段大小和最大大小。</span><span class="sxs-lookup"><span data-stu-id="249ce-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="249ce-104">从开始[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]、 可以设置段大小和最大第 0 代大小值大于`DWORD`使用[igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="249ce-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="249ce-105">语法</span><span class="sxs-lookup"><span data-stu-id="249ce-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="249ce-106">参数</span><span class="sxs-lookup"><span data-stu-id="249ce-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="249ce-107">[in]由垃圾回收系统段的大小。</span><span class="sxs-lookup"><span data-stu-id="249ce-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="249ce-108">[in]第 0 代最大大小。</span><span class="sxs-lookup"><span data-stu-id="249ce-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="249ce-109">备注</span><span class="sxs-lookup"><span data-stu-id="249ce-109">Remarks</span></span>  
 <span data-ttu-id="249ce-110">`SetGCStartupLimits`可能一次调用方法。</span><span class="sxs-lookup"><span data-stu-id="249ce-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="249ce-111">以后无法更改这些值。</span><span class="sxs-lookup"><span data-stu-id="249ce-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="249ce-112">要求</span><span class="sxs-lookup"><span data-stu-id="249ce-112">Requirements</span></span>  
 <span data-ttu-id="249ce-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="249ce-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="249ce-114">**标头：** GCHost.idl、 GCHost.h</span><span class="sxs-lookup"><span data-stu-id="249ce-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="249ce-115">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="249ce-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="249ce-116">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="249ce-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="249ce-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="249ce-117">See Also</span></span>  
 [<span data-ttu-id="249ce-118">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="249ce-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
