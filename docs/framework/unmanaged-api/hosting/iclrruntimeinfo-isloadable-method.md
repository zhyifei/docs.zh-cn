---
title: "ICLRRuntimeInfo::IsLoadable 方法"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d3825f8dc529cf9c5fbfc44ae70008695e32054
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="1b8fb-102">ICLRRuntimeInfo::IsLoadable 方法</span><span class="sxs-lookup"><span data-stu-id="1b8fb-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="1b8fb-103">指示与此接口关联的运行时是否可以加载到当前进程，并考虑可能已加载到进程的其他运行时。</span><span class="sxs-lookup"><span data-stu-id="1b8fb-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b8fb-104">语法</span><span class="sxs-lookup"><span data-stu-id="1b8fb-104">Syntax</span></span>  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b8fb-105">参数</span><span class="sxs-lookup"><span data-stu-id="1b8fb-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="1b8fb-106">[out]`true`如果此运行时可以加载到当前进程; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="1b8fb-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b8fb-107">返回值</span><span class="sxs-lookup"><span data-stu-id="1b8fb-107">Return Value</span></span>  
 <span data-ttu-id="1b8fb-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="1b8fb-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1b8fb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b8fb-109">HRESULT</span></span>|<span data-ttu-id="1b8fb-110">描述</span><span class="sxs-lookup"><span data-stu-id="1b8fb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b8fb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b8fb-111">S_OK</span></span>|<span data-ttu-id="1b8fb-112">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="1b8fb-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="1b8fb-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="1b8fb-113">E_POINTER</span></span>|<span data-ttu-id="1b8fb-114">`pbLoadable` 为 null。</span><span class="sxs-lookup"><span data-stu-id="1b8fb-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b8fb-115">备注</span><span class="sxs-lookup"><span data-stu-id="1b8fb-115">Remarks</span></span>  
 <span data-ttu-id="1b8fb-116">如果另一个运行时已加载到进程，并且与该接口关联的运行时可以加载进程内并行的执行，`pbLoadable`返回`true`。</span><span class="sxs-lookup"><span data-stu-id="1b8fb-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="1b8fb-117">如果两个运行时不能并排显示在进程内运行，`pbLoadable`返回`false`。</span><span class="sxs-lookup"><span data-stu-id="1b8fb-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="1b8fb-118">例如，公共语言运行时 (CLR) 版本 4 可以运行在同一进程中使用 CLR 版本 2.0 并行或 CLR 版本 1.1。</span><span class="sxs-lookup"><span data-stu-id="1b8fb-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="1b8fb-119">但是，CLR 版本 1.1 和 2.0 版 CLR 不能并排显示在进程内运行。</span><span class="sxs-lookup"><span data-stu-id="1b8fb-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="1b8fb-120">如果没有运行时加载到进程，此方法始终返回`true`。</span><span class="sxs-lookup"><span data-stu-id="1b8fb-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b8fb-121">惠?</span><span class="sxs-lookup"><span data-stu-id="1b8fb-121">Requirements</span></span>  
 <span data-ttu-id="1b8fb-122">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1b8fb-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b8fb-123">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="1b8fb-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1b8fb-124">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1b8fb-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b8fb-125">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b8fb-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b8fb-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b8fb-126">See Also</span></span>  
 [<span data-ttu-id="1b8fb-127">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="1b8fb-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="1b8fb-128">承载接口</span><span class="sxs-lookup"><span data-stu-id="1b8fb-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="1b8fb-129">承载</span><span class="sxs-lookup"><span data-stu-id="1b8fb-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
