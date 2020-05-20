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
ms.openlocfilehash: 4c83ffaf920abe005ba987e0a744e13aa0d3c016
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615665"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="19b93-102">ICLRErrorReportingManager::BeginCustomDump 方法</span><span class="sxs-lookup"><span data-stu-id="19b93-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="19b93-103">指定用于错误报告的自定义堆转储配置。</span><span class="sxs-lookup"><span data-stu-id="19b93-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19b93-104">语法</span><span class="sxs-lookup"><span data-stu-id="19b93-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19b93-105">参数</span><span class="sxs-lookup"><span data-stu-id="19b93-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="19b93-106">中一个[ECustomDumpFlavor](ecustomdumpflavor-enumeration.md)值，指示用于生成自定义堆转储的堆转储的种类。</span><span class="sxs-lookup"><span data-stu-id="19b93-106">[in] A [ECustomDumpFlavor](ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="19b93-107">中数组的长度 `items` 。</span><span class="sxs-lookup"><span data-stu-id="19b93-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="19b93-108">如果 `dwFlavor` 不是 DUMP_FLAVOR_Mini，则 `dwNumItems` 应为零。</span><span class="sxs-lookup"><span data-stu-id="19b93-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="19b93-109">中[CustomDumpItem](customdumpitem-structure.md)实例的数组，指定要添加到小型转储中的项。</span><span class="sxs-lookup"><span data-stu-id="19b93-109">[in] An array of [CustomDumpItem](customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="19b93-110">如果 `dwFlavor` 不 DUMP_FLAVOR_Mini，则 `items` 应为 null。</span><span class="sxs-lookup"><span data-stu-id="19b93-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="19b93-111">中保留供将来使用。</span><span class="sxs-lookup"><span data-stu-id="19b93-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19b93-112">返回值</span><span class="sxs-lookup"><span data-stu-id="19b93-112">Return Value</span></span>  
  
|<span data-ttu-id="19b93-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="19b93-113">HRESULT</span></span>|<span data-ttu-id="19b93-114">说明</span><span class="sxs-lookup"><span data-stu-id="19b93-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19b93-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="19b93-115">S_OK</span></span>|<span data-ttu-id="19b93-116">该方法已成功返回。</span><span class="sxs-lookup"><span data-stu-id="19b93-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="19b93-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="19b93-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="19b93-118">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="19b93-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="19b93-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="19b93-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="19b93-120">调用超时。</span><span class="sxs-lookup"><span data-stu-id="19b93-120">The call timed out.</span></span>|  
|<span data-ttu-id="19b93-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="19b93-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="19b93-122">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="19b93-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="19b93-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="19b93-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="19b93-124">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="19b93-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="19b93-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="19b93-125">E_FAIL</span></span>|<span data-ttu-id="19b93-126">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="19b93-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="19b93-127">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="19b93-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="19b93-128">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="19b93-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19b93-129">备注</span><span class="sxs-lookup"><span data-stu-id="19b93-129">Remarks</span></span>  
 <span data-ttu-id="19b93-130">`BeginCustomDump`方法设置自定义堆转储配置。</span><span class="sxs-lookup"><span data-stu-id="19b93-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="19b93-131">[EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md)方法清除自定义堆转储配置并释放任何关联的状态。</span><span class="sxs-lookup"><span data-stu-id="19b93-131">The [EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="19b93-132">应在自定义堆转储完成后调用它。</span><span class="sxs-lookup"><span data-stu-id="19b93-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="19b93-133">调用失败 `EndCustomDump` 会导致内存泄露。</span><span class="sxs-lookup"><span data-stu-id="19b93-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19b93-134">要求</span><span class="sxs-lookup"><span data-stu-id="19b93-134">Requirements</span></span>  
 <span data-ttu-id="19b93-135">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="19b93-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19b93-136">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="19b93-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19b93-137">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="19b93-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19b93-138">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19b93-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19b93-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19b93-139">See also</span></span>

- [<span data-ttu-id="19b93-140">CustomDumpItem 结构</span><span class="sxs-lookup"><span data-stu-id="19b93-140">CustomDumpItem Structure</span></span>](customdumpitem-structure.md)
- [<span data-ttu-id="19b93-141">ECustomDumpFlavor 枚举</span><span class="sxs-lookup"><span data-stu-id="19b93-141">ECustomDumpFlavor Enumeration</span></span>](ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="19b93-142">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="19b93-142">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
