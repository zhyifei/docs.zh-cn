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
ms.openlocfilehash: 30fca37887c17f5f0da7fd2faaba32f0e5edf235
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437360"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="0042a-102">ICLRValidator::FormatEventInfo 方法</span><span class="sxs-lookup"><span data-stu-id="0042a-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="0042a-103">获取有关指定的验证错误的详细的消息。</span><span class="sxs-lookup"><span data-stu-id="0042a-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0042a-104">语法</span><span class="sxs-lookup"><span data-stu-id="0042a-104">Syntax</span></span>  
  
```  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0042a-105">参数</span><span class="sxs-lookup"><span data-stu-id="0042a-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="0042a-106">[in]HRESULT 值传递到验证错误处理程序。</span><span class="sxs-lookup"><span data-stu-id="0042a-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="0042a-107">[in]A`VEContext`实例，其中包含有关验证错误的上下文信息。</span><span class="sxs-lookup"><span data-stu-id="0042a-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="0042a-108">[在中，out]友好错误消息中。</span><span class="sxs-lookup"><span data-stu-id="0042a-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="0042a-109">[in]错误消息的最大长度。</span><span class="sxs-lookup"><span data-stu-id="0042a-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="0042a-110">[in]安全消息中要使用其他参数的数组。</span><span class="sxs-lookup"><span data-stu-id="0042a-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0042a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="0042a-111">Return Value</span></span>  
  
|<span data-ttu-id="0042a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0042a-112">HRESULT</span></span>|<span data-ttu-id="0042a-113">描述</span><span class="sxs-lookup"><span data-stu-id="0042a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0042a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0042a-114">S_OK</span></span>|<span data-ttu-id="0042a-115">`FormatEventInfo` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0042a-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="0042a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0042a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0042a-117">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="0042a-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0042a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0042a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0042a-119">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="0042a-119">The call timed out.</span></span>|  
|<span data-ttu-id="0042a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0042a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0042a-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0042a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0042a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0042a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0042a-123">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="0042a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0042a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0042a-124">E_FAIL</span></span>|<span data-ttu-id="0042a-125">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0042a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0042a-126">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="0042a-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0042a-127">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0042a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0042a-128">要求</span><span class="sxs-lookup"><span data-stu-id="0042a-128">Requirements</span></span>  
 <span data-ttu-id="0042a-129">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0042a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0042a-130">**标头：** IValidator.idl、 IValidator.h</span><span class="sxs-lookup"><span data-stu-id="0042a-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="0042a-131">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0042a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0042a-132">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0042a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0042a-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="0042a-133">See Also</span></span>  
 [<span data-ttu-id="0042a-134">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="0042a-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="0042a-135">ICLRValidator 接口</span><span class="sxs-lookup"><span data-stu-id="0042a-135">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
