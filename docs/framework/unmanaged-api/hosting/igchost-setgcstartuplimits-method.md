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
ms.openlocfilehash: e65a83d1da0580436babd15e4f27e2db7a698668
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377600"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="20698-102">IGCHost::SetGCStartupLimits 方法</span><span class="sxs-lookup"><span data-stu-id="20698-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="20698-103">设置第 0 代段大小和最大大小。</span><span class="sxs-lookup"><span data-stu-id="20698-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="20698-104">从.NET Framework 4.5 开始，你可以设置片段的大小和最大第 0 代大小为值大于`DWORD`通过使用[IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="20698-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20698-105">语法</span><span class="sxs-lookup"><span data-stu-id="20698-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20698-106">参数</span><span class="sxs-lookup"><span data-stu-id="20698-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="20698-107">[in]由垃圾回收系统段的大小。</span><span class="sxs-lookup"><span data-stu-id="20698-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="20698-108">[in]第 0 代最大大小。</span><span class="sxs-lookup"><span data-stu-id="20698-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20698-109">备注</span><span class="sxs-lookup"><span data-stu-id="20698-109">Remarks</span></span>  
 <span data-ttu-id="20698-110">`SetGCStartupLimits`可能只有一次调用方法。</span><span class="sxs-lookup"><span data-stu-id="20698-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="20698-111">以后无法更改这些值。</span><span class="sxs-lookup"><span data-stu-id="20698-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20698-112">要求</span><span class="sxs-lookup"><span data-stu-id="20698-112">Requirements</span></span>  
 <span data-ttu-id="20698-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="20698-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20698-114">**标头：** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="20698-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="20698-115">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="20698-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20698-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20698-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20698-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="20698-117">See also</span></span>

- [<span data-ttu-id="20698-118">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="20698-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
