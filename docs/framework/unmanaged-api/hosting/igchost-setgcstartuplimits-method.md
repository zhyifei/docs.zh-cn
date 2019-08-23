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
ms.openlocfilehash: 87ba947b9564f82f8daf8cd2ba0acac5cc3587ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928665"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="7e619-102">IGCHost::SetGCStartupLimits 方法</span><span class="sxs-lookup"><span data-stu-id="7e619-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="7e619-103">设置第0代的段大小和最大大小。</span><span class="sxs-lookup"><span data-stu-id="7e619-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7e619-104">从 .NET Framework 4.5 开始, 可以使用[IGCHost2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)方法将段大小和最大第 0 `DWORD`代大小设置为大于的值。</span><span class="sxs-lookup"><span data-stu-id="7e619-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e619-105">语法</span><span class="sxs-lookup"><span data-stu-id="7e619-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e619-106">参数</span><span class="sxs-lookup"><span data-stu-id="7e619-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="7e619-107">中垃圾收集系统使用的段大小。</span><span class="sxs-lookup"><span data-stu-id="7e619-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="7e619-108">中第0代的最大大小。</span><span class="sxs-lookup"><span data-stu-id="7e619-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e619-109">备注</span><span class="sxs-lookup"><span data-stu-id="7e619-109">Remarks</span></span>  
 <span data-ttu-id="7e619-110">`SetGCStartupLimits`方法只能调用一次。</span><span class="sxs-lookup"><span data-stu-id="7e619-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="7e619-111">以后不能更改这些值。</span><span class="sxs-lookup"><span data-stu-id="7e619-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e619-112">要求</span><span class="sxs-lookup"><span data-stu-id="7e619-112">Requirements</span></span>  
 <span data-ttu-id="7e619-113">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7e619-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e619-114">**标头：** GCHost, GCHost</span><span class="sxs-lookup"><span data-stu-id="7e619-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="7e619-115">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="7e619-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e619-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e619-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e619-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e619-117">See also</span></span>

- [<span data-ttu-id="7e619-118">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="7e619-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
