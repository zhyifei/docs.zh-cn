---
title: ICLRDebugManager::IsDebuggerAttached 方法
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type:
- apiref
ms.openlocfilehash: a21391f52a27e7f7a3abe533499c6b2581ec4a73
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615734"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="883ef-102">ICLRDebugManager::IsDebuggerAttached 方法</span><span class="sxs-lookup"><span data-stu-id="883ef-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="883ef-103">获取一个值，它指示调试器是否已附加到进程。</span><span class="sxs-lookup"><span data-stu-id="883ef-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="883ef-104">语法</span><span class="sxs-lookup"><span data-stu-id="883ef-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="883ef-105">参数</span><span class="sxs-lookup"><span data-stu-id="883ef-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="883ef-106">[out] `true`如果调试器附加到进程，则为; 否则为。否则为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="883ef-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="883ef-107">返回值</span><span class="sxs-lookup"><span data-stu-id="883ef-107">Return Value</span></span>  
  
|<span data-ttu-id="883ef-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="883ef-108">HRESULT</span></span>|<span data-ttu-id="883ef-109">说明</span><span class="sxs-lookup"><span data-stu-id="883ef-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="883ef-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="883ef-110">S_OK</span></span>|<span data-ttu-id="883ef-111">`IsDebuggerAttached`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="883ef-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="883ef-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="883ef-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="883ef-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="883ef-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="883ef-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="883ef-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="883ef-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="883ef-115">The call timed out.</span></span>|  
|<span data-ttu-id="883ef-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="883ef-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="883ef-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="883ef-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="883ef-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="883ef-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="883ef-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="883ef-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="883ef-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="883ef-120">E_FAIL</span></span>|<span data-ttu-id="883ef-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="883ef-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="883ef-122">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="883ef-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="883ef-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="883ef-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="883ef-124">备注</span><span class="sxs-lookup"><span data-stu-id="883ef-124">Remarks</span></span>  
 <span data-ttu-id="883ef-125">`IsDebuggerAttached`允许宿主查询 CLR 以确定调试器是否已附加到进程。</span><span class="sxs-lookup"><span data-stu-id="883ef-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="883ef-126">要求</span><span class="sxs-lookup"><span data-stu-id="883ef-126">Requirements</span></span>  
 <span data-ttu-id="883ef-127">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="883ef-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="883ef-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="883ef-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="883ef-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="883ef-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="883ef-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="883ef-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="883ef-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="883ef-131">See also</span></span>

- [<span data-ttu-id="883ef-132">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="883ef-132">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="883ef-133">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="883ef-133">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="883ef-134">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="883ef-134">IHostControl Interface</span></span>](ihostcontrol-interface.md)
