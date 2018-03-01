---
title: "IGCHost2::SetGCStartupLimitsEx 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IGCHost2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2::SetGCStartupLimitsEx
helpviewer_keywords:
- IGCHost2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, IGCHost2 interface [.NET Framework hosting]
ms.assetid: bba941c2-1c57-46d3-bbf5-5fb92700c490
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f8ed2b2aa43fcf925b6202ab339209904e7c53af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="cff91-102">IGCHost2::SetGCStartupLimitsEx 方法</span><span class="sxs-lookup"><span data-stu-id="cff91-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="cff91-103">为第 0 代中设置的段大小和最大大小。</span><span class="sxs-lookup"><span data-stu-id="cff91-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cff91-104">语法</span><span class="sxs-lookup"><span data-stu-id="cff91-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cff91-105">参数</span><span class="sxs-lookup"><span data-stu-id="cff91-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="cff91-106">[in]由垃圾回收系统段的大小。</span><span class="sxs-lookup"><span data-stu-id="cff91-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="cff91-107">[in]第 0 代最大大小。</span><span class="sxs-lookup"><span data-stu-id="cff91-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cff91-108">备注</span><span class="sxs-lookup"><span data-stu-id="cff91-108">Remarks</span></span>  
 <span data-ttu-id="cff91-109">值的`SetGCStartupLimitsEx`仅之前启动主机时，可以指定集。</span><span class="sxs-lookup"><span data-stu-id="cff91-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="cff91-110">以后无法更改这些值。</span><span class="sxs-lookup"><span data-stu-id="cff91-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cff91-111">惠?</span><span class="sxs-lookup"><span data-stu-id="cff91-111">Requirements</span></span>  
 <span data-ttu-id="cff91-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cff91-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cff91-113">**标头：** GCHost.idl、 GCHost.h</span><span class="sxs-lookup"><span data-stu-id="cff91-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="cff91-114">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cff91-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cff91-115">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cff91-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff91-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="cff91-116">See Also</span></span>  
 [<span data-ttu-id="cff91-117">IGCHost2 接口</span><span class="sxs-lookup"><span data-stu-id="cff91-117">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
