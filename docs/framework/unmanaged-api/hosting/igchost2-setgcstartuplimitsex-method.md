---
title: IGCHost2::SetGCStartupLimitsEx 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: ca9566168b8aae361af8d61539066624697a2d04
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805148"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="be421-102">IGCHost2::SetGCStartupLimitsEx 方法</span><span class="sxs-lookup"><span data-stu-id="be421-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="be421-103">设置第0代的段大小和最大大小。</span><span class="sxs-lookup"><span data-stu-id="be421-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be421-104">语法</span><span class="sxs-lookup"><span data-stu-id="be421-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be421-105">参数</span><span class="sxs-lookup"><span data-stu-id="be421-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="be421-106">中垃圾收集系统使用的段大小。</span><span class="sxs-lookup"><span data-stu-id="be421-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="be421-107">中第0代的最大大小。</span><span class="sxs-lookup"><span data-stu-id="be421-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be421-108">备注</span><span class="sxs-lookup"><span data-stu-id="be421-108">Remarks</span></span>  
 <span data-ttu-id="be421-109">`SetGCStartupLimitsEx`只能在启动主机之前指定设置的值。</span><span class="sxs-lookup"><span data-stu-id="be421-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="be421-110">以后不能更改这些值。</span><span class="sxs-lookup"><span data-stu-id="be421-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be421-111">要求</span><span class="sxs-lookup"><span data-stu-id="be421-111">Requirements</span></span>  
 <span data-ttu-id="be421-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="be421-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be421-113">**标头：** GCHost，GCHost</span><span class="sxs-lookup"><span data-stu-id="be421-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="be421-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="be421-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be421-115">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be421-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be421-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be421-116">See also</span></span>

- [<span data-ttu-id="be421-117">IGCHost2 接口</span><span class="sxs-lookup"><span data-stu-id="be421-117">IGCHost2 Interface</span></span>](igchost2-interface.md)
