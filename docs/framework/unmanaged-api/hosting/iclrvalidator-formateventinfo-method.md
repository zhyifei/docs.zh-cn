---
title: ICLRValidator::FormatEventInfo 方法
ms.date: 03/30/2017
api_name:
- ICLRValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::FormatEventInfo
helpviewer_keywords:
- FormatEventInfo method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::FormatEventInfo method [.NET Framework hosting]
ms.assetid: 808e1f1d-52f4-47c4-83cc-dcf47d075219
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9117a82dff48dcda8d96f0feb7b8c4a001fa17f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59205870"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="46b1e-102">ICLRValidator::FormatEventInfo 方法</span><span class="sxs-lookup"><span data-stu-id="46b1e-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="46b1e-103">获取有关指定的验证错误的详细的消息。</span><span class="sxs-lookup"><span data-stu-id="46b1e-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46b1e-104">语法</span><span class="sxs-lookup"><span data-stu-id="46b1e-104">Syntax</span></span>  
  
```  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46b1e-105">参数</span><span class="sxs-lookup"><span data-stu-id="46b1e-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="46b1e-106">[in]HRESULT 值传递给验证错误处理程序。</span><span class="sxs-lookup"><span data-stu-id="46b1e-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="46b1e-107">[in]一个`VEContext`实例，其中包含有关验证错误的上下文信息。</span><span class="sxs-lookup"><span data-stu-id="46b1e-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="46b1e-108">[in、 out]友好的错误消息中。</span><span class="sxs-lookup"><span data-stu-id="46b1e-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="46b1e-109">[in]错误消息的最大长度。</span><span class="sxs-lookup"><span data-stu-id="46b1e-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="46b1e-110">[in]要在消息中使用的其他参数的安全数组。</span><span class="sxs-lookup"><span data-stu-id="46b1e-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46b1e-111">返回值</span><span class="sxs-lookup"><span data-stu-id="46b1e-111">Return Value</span></span>  
  
|<span data-ttu-id="46b1e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="46b1e-112">HRESULT</span></span>|<span data-ttu-id="46b1e-113">描述</span><span class="sxs-lookup"><span data-stu-id="46b1e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="46b1e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="46b1e-114">S_OK</span></span>|<span data-ttu-id="46b1e-115">`FormatEventInfo` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="46b1e-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="46b1e-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="46b1e-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="46b1e-117">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="46b1e-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="46b1e-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="46b1e-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="46b1e-119">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="46b1e-119">The call timed out.</span></span>|  
|<span data-ttu-id="46b1e-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="46b1e-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="46b1e-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="46b1e-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="46b1e-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="46b1e-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="46b1e-123">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="46b1e-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="46b1e-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="46b1e-124">E_FAIL</span></span>|<span data-ttu-id="46b1e-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="46b1e-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="46b1e-126">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="46b1e-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="46b1e-127">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="46b1e-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="46b1e-128">要求</span><span class="sxs-lookup"><span data-stu-id="46b1e-128">Requirements</span></span>  
 <span data-ttu-id="46b1e-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="46b1e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46b1e-130">**标头：** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="46b1e-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="46b1e-131">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="46b1e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="46b1e-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46b1e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46b1e-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="46b1e-133">See also</span></span>

- [<span data-ttu-id="46b1e-134">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="46b1e-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="46b1e-135">ICLRValidator 接口</span><span class="sxs-lookup"><span data-stu-id="46b1e-135">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
