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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9780020abe609212fe3c4bd65f70200467ff9c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54533684"
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="17389-102">ICLRRuntimeInfo::IsLoadable 方法</span><span class="sxs-lookup"><span data-stu-id="17389-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="17389-103">指示与此接口关联的运行时是否可以加载到当前进程中，考虑到可能已加载到进程的其他运行时。</span><span class="sxs-lookup"><span data-stu-id="17389-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17389-104">语法</span><span class="sxs-lookup"><span data-stu-id="17389-104">Syntax</span></span>  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17389-105">参数</span><span class="sxs-lookup"><span data-stu-id="17389-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="17389-106">[out]`true`如果此运行时可以加载到当前进程; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="17389-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17389-107">返回值</span><span class="sxs-lookup"><span data-stu-id="17389-107">Return Value</span></span>  
 <span data-ttu-id="17389-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="17389-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="17389-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="17389-109">HRESULT</span></span>|<span data-ttu-id="17389-110">描述</span><span class="sxs-lookup"><span data-stu-id="17389-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="17389-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="17389-111">S_OK</span></span>|<span data-ttu-id="17389-112">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="17389-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="17389-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="17389-113">E_POINTER</span></span>|<span data-ttu-id="17389-114">`pbLoadable` 为 null。</span><span class="sxs-lookup"><span data-stu-id="17389-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17389-115">备注</span><span class="sxs-lookup"><span data-stu-id="17389-115">Remarks</span></span>  
 <span data-ttu-id="17389-116">如果另一个运行时已加载到进程，并且与此接口关联的运行时可以加载过程中通过并行执行`pbLoadable`返回`true`。</span><span class="sxs-lookup"><span data-stu-id="17389-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="17389-117">如果两个运行时不能通过并行进程中运行，`pbLoadable`返回`false`。</span><span class="sxs-lookup"><span data-stu-id="17389-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="17389-118">例如，公共语言运行时 (CLR) 版本 4 可以运行与 CLR 2.0 版本在同一进程中并行或 CLR 版本 1.1。</span><span class="sxs-lookup"><span data-stu-id="17389-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="17389-119">但是，CLR 版本 1.1 和 CLR 版本 2.0 不能通过并行进程中运行。</span><span class="sxs-lookup"><span data-stu-id="17389-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="17389-120">如果没有运行时加载到进程，此方法始终返回`true`。</span><span class="sxs-lookup"><span data-stu-id="17389-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17389-121">要求</span><span class="sxs-lookup"><span data-stu-id="17389-121">Requirements</span></span>  
 <span data-ttu-id="17389-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="17389-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17389-123">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="17389-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="17389-124">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="17389-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17389-125">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17389-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17389-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="17389-126">See also</span></span>
- [<span data-ttu-id="17389-127">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="17389-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="17389-128">承载接口</span><span class="sxs-lookup"><span data-stu-id="17389-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="17389-129">承载</span><span class="sxs-lookup"><span data-stu-id="17389-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
