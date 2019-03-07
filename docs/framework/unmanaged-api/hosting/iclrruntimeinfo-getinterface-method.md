---
title: ICLRRuntimeInfo::GetInterface 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81f27489d554b59101f1eb181ea64f6b68da979c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491901"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="5bdd4-102">ICLRRuntimeInfo::GetInterface 方法</span><span class="sxs-lookup"><span data-stu-id="5bdd4-102">ICLRRuntimeInfo::GetInterface Method</span></span>
<span data-ttu-id="5bdd4-103">将 CLR 加载到当前进程，并返回运行时接口指针，如[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)， [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)，并[IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="5bdd4-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), and [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="5bdd4-104">此方法取代了所有`CorBindTo`\* 中的函数[弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)部分。</span><span class="sxs-lookup"><span data-stu-id="5bdd4-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bdd4-105">语法</span><span class="sxs-lookup"><span data-stu-id="5bdd4-105">Syntax</span></span>  
  
```  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bdd4-106">参数</span><span class="sxs-lookup"><span data-stu-id="5bdd4-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="5bdd4-107">[in]用于 coclass 的 CLSID 接口。</span><span class="sxs-lookup"><span data-stu-id="5bdd4-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="5bdd4-108">[in]所请求的 IID`rclsid`接口。</span><span class="sxs-lookup"><span data-stu-id="5bdd4-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="5bdd4-109">[out]指向查询的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="5bdd4-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5bdd4-110">返回值</span><span class="sxs-lookup"><span data-stu-id="5bdd4-110">Return Value</span></span>  
 <span data-ttu-id="5bdd4-111">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="5bdd4-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5bdd4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5bdd4-112">HRESULT</span></span>|<span data-ttu-id="5bdd4-113">描述</span><span class="sxs-lookup"><span data-stu-id="5bdd4-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5bdd4-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="5bdd4-114">S_OK</span></span>|<span data-ttu-id="5bdd4-115">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="5bdd4-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="5bdd4-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="5bdd4-116">E_POINTER</span></span>|<span data-ttu-id="5bdd4-117">`ppUnk` 为 null。</span><span class="sxs-lookup"><span data-stu-id="5bdd4-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="5bdd4-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5bdd4-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="5bdd4-119">没有足够的内存是可用来处理该请求。</span><span class="sxs-lookup"><span data-stu-id="5bdd4-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="5bdd4-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="5bdd4-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="5bdd4-121">不同的运行时已绑定到旧的 CLR 版本 2 激活策略。</span><span class="sxs-lookup"><span data-stu-id="5bdd4-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bdd4-122">备注</span><span class="sxs-lookup"><span data-stu-id="5bdd4-122">Remarks</span></span>  
 <span data-ttu-id="5bdd4-123">此方法会导致 CLR 加载，但未初始化。</span><span class="sxs-lookup"><span data-stu-id="5bdd4-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="5bdd4-124">下表显示了受支持的组合`rclsid`和`riid`。</span><span class="sxs-lookup"><span data-stu-id="5bdd4-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="5bdd4-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="5bdd4-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="5bdd4-126">IID_IMetaDataDispenser IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="5bdd4-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="5bdd4-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="5bdd4-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="5bdd4-128">IID_IMetaDataDispenser IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="5bdd4-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="5bdd4-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="5bdd4-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="5bdd4-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="5bdd4-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="5bdd4-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="5bdd4-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="5bdd4-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="5bdd4-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="5bdd4-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="5bdd4-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="5bdd4-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="5bdd4-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="5bdd4-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="5bdd4-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="5bdd4-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="5bdd4-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="5bdd4-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="5bdd4-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="5bdd4-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="5bdd4-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5bdd4-139">要求</span><span class="sxs-lookup"><span data-stu-id="5bdd4-139">Requirements</span></span>  
 <span data-ttu-id="5bdd4-140">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5bdd4-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bdd4-141">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5bdd4-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5bdd4-142">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5bdd4-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5bdd4-143">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bdd4-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bdd4-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="5bdd4-144">See also</span></span>
- [<span data-ttu-id="5bdd4-145">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="5bdd4-145">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="5bdd4-146">承载接口</span><span class="sxs-lookup"><span data-stu-id="5bdd4-146">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="5bdd4-147">承载</span><span class="sxs-lookup"><span data-stu-id="5bdd4-147">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
