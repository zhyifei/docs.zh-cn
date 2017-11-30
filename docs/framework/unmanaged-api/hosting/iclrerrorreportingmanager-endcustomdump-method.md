---
title: "ICLRErrorReportingManager::EndCustomDump 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager.EndCustomDump
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager::EndCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::EndCustomDump method [.NET Framework hosting]
- EndCustomDump method [.NET Framework hosting]
ms.assetid: 88a5da04-8729-4108-82c4-af206a7d483e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 059ab01d3cc05bac84bb1a4cd8fffc7fc259ed60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="21839-102">ICLRErrorReportingManager::EndCustomDump 方法</span><span class="sxs-lookup"><span data-stu-id="21839-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>
<span data-ttu-id="21839-103">将删除已在以前调用中指定的自定义堆栈转储配置[iclrerrorreportingmanager:: Begincustomdump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="21839-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21839-104">语法</span><span class="sxs-lookup"><span data-stu-id="21839-104">Syntax</span></span>  
  
```  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="21839-105">返回值</span><span class="sxs-lookup"><span data-stu-id="21839-105">Return Value</span></span>  
  
|<span data-ttu-id="21839-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="21839-106">HRESULT</span></span>|<span data-ttu-id="21839-107">描述</span><span class="sxs-lookup"><span data-stu-id="21839-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="21839-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="21839-108">S_OK</span></span>|<span data-ttu-id="21839-109">`EndCustomDump`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="21839-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="21839-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="21839-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="21839-111">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="21839-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="21839-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="21839-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="21839-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="21839-113">The call timed out.</span></span>|  
|<span data-ttu-id="21839-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="21839-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="21839-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="21839-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="21839-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="21839-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="21839-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="21839-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="21839-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="21839-118">E_FAIL</span></span>|<span data-ttu-id="21839-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="21839-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="21839-120">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="21839-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="21839-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="21839-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21839-122">备注</span><span class="sxs-lookup"><span data-stu-id="21839-122">Remarks</span></span>  
 <span data-ttu-id="21839-123">`EndCustomDump`方法将清除自定义堆栈转储的配置设置的以前调用`BeginCustomDump`方法并释放任何关联的状态。</span><span class="sxs-lookup"><span data-stu-id="21839-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="21839-124">自定义堆栈转储完成之后才调用它。</span><span class="sxs-lookup"><span data-stu-id="21839-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="21839-125">调用失败`EndCustomDump`导致内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="21839-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21839-126">要求</span><span class="sxs-lookup"><span data-stu-id="21839-126">Requirements</span></span>  
 <span data-ttu-id="21839-127">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="21839-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21839-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="21839-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21839-129">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="21839-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21839-130">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21839-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21839-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21839-131">See Also</span></span>  
 [<span data-ttu-id="21839-132">CustomDumpItem 结构</span><span class="sxs-lookup"><span data-stu-id="21839-132">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 [<span data-ttu-id="21839-133">ECustomDumpFlavor 枚举</span><span class="sxs-lookup"><span data-stu-id="21839-133">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)  
 [<span data-ttu-id="21839-134">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="21839-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
