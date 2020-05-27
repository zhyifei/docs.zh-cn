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
ms.openlocfilehash: 3b0c11ac9d827bd252018172e2337df653054a7b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805205"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="1efde-102">IGCHost::SetGCStartupLimits 方法</span><span class="sxs-lookup"><span data-stu-id="1efde-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="1efde-103">设置第0代的段大小和最大大小。</span><span class="sxs-lookup"><span data-stu-id="1efde-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1efde-104">从 .NET Framework 4.5 开始，可以 `DWORD` 使用[IGCHost2：： SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md)方法将段大小和最大第0代大小设置为大于的值。</span><span class="sxs-lookup"><span data-stu-id="1efde-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1efde-105">语法</span><span class="sxs-lookup"><span data-stu-id="1efde-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1efde-106">参数</span><span class="sxs-lookup"><span data-stu-id="1efde-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="1efde-107">中垃圾收集系统使用的段大小。</span><span class="sxs-lookup"><span data-stu-id="1efde-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="1efde-108">中第0代的最大大小。</span><span class="sxs-lookup"><span data-stu-id="1efde-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1efde-109">备注</span><span class="sxs-lookup"><span data-stu-id="1efde-109">Remarks</span></span>  
 <span data-ttu-id="1efde-110">`SetGCStartupLimits`方法只能调用一次。</span><span class="sxs-lookup"><span data-stu-id="1efde-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="1efde-111">以后不能更改这些值。</span><span class="sxs-lookup"><span data-stu-id="1efde-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1efde-112">要求</span><span class="sxs-lookup"><span data-stu-id="1efde-112">Requirements</span></span>  
 <span data-ttu-id="1efde-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1efde-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1efde-114">**标头：** GCHost，GCHost</span><span class="sxs-lookup"><span data-stu-id="1efde-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="1efde-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="1efde-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1efde-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1efde-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1efde-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1efde-117">See also</span></span>

- [<span data-ttu-id="1efde-118">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="1efde-118">IGCHost Interface</span></span>](igchost-interface.md)
