---
title: ICLRRuntimeInfo::IsLoadable 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
ms.openlocfilehash: 9339bb974c261e62502c760dfaf45651573cbe1a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136377"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="ef665-102">ICLRRuntimeInfo::IsLoadable 方法</span><span class="sxs-lookup"><span data-stu-id="ef665-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="ef665-103">指示是否可将与此接口关联的运行时加载到当前进程，并考虑可能已加载到进程中的其他运行时。</span><span class="sxs-lookup"><span data-stu-id="ef665-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef665-104">语法</span><span class="sxs-lookup"><span data-stu-id="ef665-104">Syntax</span></span>  
  
```cpp  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef665-105">参数</span><span class="sxs-lookup"><span data-stu-id="ef665-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="ef665-106">[out] 如果可以将此运行时加载到当前进程，则 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="ef665-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef665-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ef665-107">Return Value</span></span>  
 <span data-ttu-id="ef665-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="ef665-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ef665-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ef665-109">HRESULT</span></span>|<span data-ttu-id="ef665-110">描述</span><span class="sxs-lookup"><span data-stu-id="ef665-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ef665-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ef665-111">S_OK</span></span>|<span data-ttu-id="ef665-112">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="ef665-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="ef665-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ef665-113">E_POINTER</span></span>|<span data-ttu-id="ef665-114">`pbLoadable` 为 null。</span><span class="sxs-lookup"><span data-stu-id="ef665-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef665-115">备注</span><span class="sxs-lookup"><span data-stu-id="ef665-115">Remarks</span></span>  
 <span data-ttu-id="ef665-116">如果已将另一个运行时加载到进程中，并且可以为进程内并行执行加载与此接口关联的运行时，`pbLoadable` 将返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="ef665-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="ef665-117">如果两个运行时不能并行运行，`pbLoadable` 将返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="ef665-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="ef665-118">例如，公共语言运行时（CLR）版本4可在 CLR 版本2.0 或 CLR 版本1.1 的同一进程中并行运行。</span><span class="sxs-lookup"><span data-stu-id="ef665-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="ef665-119">但是，CLR 版本1.1 和 CLR 版本2.0 无法在进程中并行运行。</span><span class="sxs-lookup"><span data-stu-id="ef665-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="ef665-120">如果没有任何运行时加载到进程中，则此方法始终返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="ef665-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef665-121">要求</span><span class="sxs-lookup"><span data-stu-id="ef665-121">Requirements</span></span>  
 <span data-ttu-id="ef665-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ef665-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef665-123">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="ef665-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ef665-124">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="ef665-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef665-125">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef665-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef665-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef665-126">See also</span></span>

- [<span data-ttu-id="ef665-127">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="ef665-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="ef665-128">承载接口</span><span class="sxs-lookup"><span data-stu-id="ef665-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ef665-129">承载</span><span class="sxs-lookup"><span data-stu-id="ef665-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
