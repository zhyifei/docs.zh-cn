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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5e14749c3596ad22a435a11f75c928110c434de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196601"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="5ef23-102">ICLRErrorReportingManager::EndCustomDump 方法</span><span class="sxs-lookup"><span data-stu-id="5ef23-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>
<span data-ttu-id="5ef23-103">在早期调用中指定的自定义的堆栈转储配置中删除[iclrerrorreportingmanager:: Begincustomdump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5ef23-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ef23-104">语法</span><span class="sxs-lookup"><span data-stu-id="5ef23-104">Syntax</span></span>  
  
```  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5ef23-105">返回值</span><span class="sxs-lookup"><span data-stu-id="5ef23-105">Return Value</span></span>  
  
|<span data-ttu-id="5ef23-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5ef23-106">HRESULT</span></span>|<span data-ttu-id="5ef23-107">描述</span><span class="sxs-lookup"><span data-stu-id="5ef23-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5ef23-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5ef23-108">S_OK</span></span>|<span data-ttu-id="5ef23-109">`EndCustomDump` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="5ef23-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="5ef23-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5ef23-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5ef23-111">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="5ef23-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5ef23-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5ef23-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5ef23-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="5ef23-113">The call timed out.</span></span>|  
|<span data-ttu-id="5ef23-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5ef23-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5ef23-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="5ef23-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5ef23-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5ef23-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5ef23-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="5ef23-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5ef23-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5ef23-118">E_FAIL</span></span>|<span data-ttu-id="5ef23-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="5ef23-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5ef23-120">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="5ef23-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5ef23-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="5ef23-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ef23-122">备注</span><span class="sxs-lookup"><span data-stu-id="5ef23-122">Remarks</span></span>  
 <span data-ttu-id="5ef23-123">`EndCustomDump`方法将清除设置到的早期调用的自定义的堆栈转储配置`BeginCustomDump`方法，并释放任何关联的状态。</span><span class="sxs-lookup"><span data-stu-id="5ef23-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="5ef23-124">自定义的堆栈转储完成后，应调用它。</span><span class="sxs-lookup"><span data-stu-id="5ef23-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5ef23-125">调用失败`EndCustomDump`导致内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="5ef23-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ef23-126">要求</span><span class="sxs-lookup"><span data-stu-id="5ef23-126">Requirements</span></span>  
 <span data-ttu-id="5ef23-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5ef23-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ef23-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5ef23-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5ef23-129">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5ef23-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5ef23-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ef23-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ef23-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ef23-131">See also</span></span>

- [<span data-ttu-id="5ef23-132">CustomDumpItem 结构</span><span class="sxs-lookup"><span data-stu-id="5ef23-132">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="5ef23-133">ECustomDumpFlavor 枚举</span><span class="sxs-lookup"><span data-stu-id="5ef23-133">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="5ef23-134">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="5ef23-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
