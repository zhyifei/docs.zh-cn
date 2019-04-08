---
title: ICLRErrorReportingManager::BeginCustomDump 方法
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cb6cd8d31e01ea2f1749a6cb4d17173679f0c06
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104105"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="30a80-102">ICLRErrorReportingManager::BeginCustomDump 方法</span><span class="sxs-lookup"><span data-stu-id="30a80-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="30a80-103">指定的错误报告的自定义堆转储的配置。</span><span class="sxs-lookup"><span data-stu-id="30a80-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30a80-104">语法</span><span class="sxs-lookup"><span data-stu-id="30a80-104">Syntax</span></span>  
  
```  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30a80-105">参数</span><span class="sxs-lookup"><span data-stu-id="30a80-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="30a80-106">[in]一个[ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)值，该值指示在其上构建自定义堆转储的堆转储的类型。</span><span class="sxs-lookup"><span data-stu-id="30a80-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="30a80-107">[in]长度`items`数组。</span><span class="sxs-lookup"><span data-stu-id="30a80-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="30a80-108">如果`dwFlavor`不是 DUMP_FLAVOR_Mini，`dwNumItems`应为零。</span><span class="sxs-lookup"><span data-stu-id="30a80-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="30a80-109">[in]一个数组[CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)实例，指定要添加到小型转储的项。</span><span class="sxs-lookup"><span data-stu-id="30a80-109">[in] An array of [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="30a80-110">如果`dwFlavor`不是 DUMP_FLAVOR_Mini，`items`应为 null。</span><span class="sxs-lookup"><span data-stu-id="30a80-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="30a80-111">[in]保留供将来使用。</span><span class="sxs-lookup"><span data-stu-id="30a80-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30a80-112">返回值</span><span class="sxs-lookup"><span data-stu-id="30a80-112">Return Value</span></span>  
  
|<span data-ttu-id="30a80-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30a80-113">HRESULT</span></span>|<span data-ttu-id="30a80-114">描述</span><span class="sxs-lookup"><span data-stu-id="30a80-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30a80-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="30a80-115">S_OK</span></span>|<span data-ttu-id="30a80-116">该方法成功返回。</span><span class="sxs-lookup"><span data-stu-id="30a80-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="30a80-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="30a80-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="30a80-118">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="30a80-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="30a80-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="30a80-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="30a80-120">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="30a80-120">The call timed out.</span></span>|  
|<span data-ttu-id="30a80-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="30a80-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="30a80-122">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="30a80-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="30a80-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="30a80-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="30a80-124">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="30a80-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="30a80-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="30a80-125">E_FAIL</span></span>|<span data-ttu-id="30a80-126">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="30a80-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="30a80-127">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="30a80-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="30a80-128">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="30a80-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30a80-129">备注</span><span class="sxs-lookup"><span data-stu-id="30a80-129">Remarks</span></span>  
 <span data-ttu-id="30a80-130">`BeginCustomDump`方法设置自定义堆转储配置。</span><span class="sxs-lookup"><span data-stu-id="30a80-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="30a80-131">[EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)方法清除自定义堆转储配置，并释放任何关联的状态。</span><span class="sxs-lookup"><span data-stu-id="30a80-131">The [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="30a80-132">自定义堆转储完成后，应调用它。</span><span class="sxs-lookup"><span data-stu-id="30a80-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="30a80-133">调用失败`EndCustomDump`导致内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="30a80-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30a80-134">要求</span><span class="sxs-lookup"><span data-stu-id="30a80-134">Requirements</span></span>  
 <span data-ttu-id="30a80-135">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="30a80-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30a80-136">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="30a80-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30a80-137">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="30a80-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="30a80-138">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="30a80-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="30a80-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="30a80-139">See also</span></span>

- [<span data-ttu-id="30a80-140">CustomDumpItem 结构</span><span class="sxs-lookup"><span data-stu-id="30a80-140">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="30a80-141">ECustomDumpFlavor 枚举</span><span class="sxs-lookup"><span data-stu-id="30a80-141">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="30a80-142">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="30a80-142">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
