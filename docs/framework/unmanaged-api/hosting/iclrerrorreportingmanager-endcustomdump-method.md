---
title: ICLRErrorReportingManager::EndCustomDump 方法
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.EndCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::EndCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::EndCustomDump method [.NET Framework hosting]
- EndCustomDump method [.NET Framework hosting]
ms.assetid: 88a5da04-8729-4108-82c4-af206a7d483e
topic_type:
- apiref
ms.openlocfilehash: 2acbe72377e4c5b291ab062fcb5faa6503bd7937
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129290"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="ea309-102">ICLRErrorReportingManager::EndCustomDump 方法</span><span class="sxs-lookup"><span data-stu-id="ea309-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>
<span data-ttu-id="ea309-103">删除在先前对[ICLRErrorReportingManager：： BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)方法的调用中指定的自定义堆栈转储配置。</span><span class="sxs-lookup"><span data-stu-id="ea309-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea309-104">语法</span><span class="sxs-lookup"><span data-stu-id="ea309-104">Syntax</span></span>  
  
```cpp  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ea309-105">返回值</span><span class="sxs-lookup"><span data-stu-id="ea309-105">Return Value</span></span>  
  
|<span data-ttu-id="ea309-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ea309-106">HRESULT</span></span>|<span data-ttu-id="ea309-107">描述</span><span class="sxs-lookup"><span data-stu-id="ea309-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ea309-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ea309-108">S_OK</span></span>|<span data-ttu-id="ea309-109">`EndCustomDump` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="ea309-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="ea309-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ea309-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ea309-111">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ea309-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ea309-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ea309-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ea309-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="ea309-113">The call timed out.</span></span>|  
|<span data-ttu-id="ea309-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ea309-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ea309-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ea309-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ea309-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ea309-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ea309-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="ea309-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ea309-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ea309-118">E_FAIL</span></span>|<span data-ttu-id="ea309-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ea309-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ea309-120">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="ea309-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ea309-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ea309-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea309-122">备注</span><span class="sxs-lookup"><span data-stu-id="ea309-122">Remarks</span></span>  
 <span data-ttu-id="ea309-123">`EndCustomDump` 方法通过之前对 `BeginCustomDump` 方法的调用来清除自定义堆栈转储配置，并释放任何关联的状态。</span><span class="sxs-lookup"><span data-stu-id="ea309-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="ea309-124">应在自定义堆栈转储完成后调用它。</span><span class="sxs-lookup"><span data-stu-id="ea309-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ea309-125">未能调用 `EndCustomDump` 会导致内存泄露。</span><span class="sxs-lookup"><span data-stu-id="ea309-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea309-126">要求</span><span class="sxs-lookup"><span data-stu-id="ea309-126">Requirements</span></span>  
 <span data-ttu-id="ea309-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ea309-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea309-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ea309-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ea309-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="ea309-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea309-130">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea309-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea309-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea309-131">See also</span></span>

- [<span data-ttu-id="ea309-132">CustomDumpItem 结构</span><span class="sxs-lookup"><span data-stu-id="ea309-132">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="ea309-133">ECustomDumpFlavor 枚举</span><span class="sxs-lookup"><span data-stu-id="ea309-133">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="ea309-134">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="ea309-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
