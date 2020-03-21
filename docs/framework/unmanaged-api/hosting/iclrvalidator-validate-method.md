---
title: ICLRValidator::Validate 方法
ms.date: 03/30/2017
api_name:
- ICLRValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type:
- apiref
ms.openlocfilehash: 427895ffea94e6c657d775ebdeb8571070a61c6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178063"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="cc3b5-102">ICLRValidator::Validate 方法</span><span class="sxs-lookup"><span data-stu-id="cc3b5-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="cc3b5-103">验证指定文件中的可移植可执行 （PE） 或 Microsoft 中间语言 （MSIL）。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc3b5-104">语法</span><span class="sxs-lookup"><span data-stu-id="cc3b5-104">Syntax</span></span>  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="cc3b5-105">parameters</span><span class="sxs-lookup"><span data-stu-id="cc3b5-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="cc3b5-106">[在]指向处理验证错误的`IVEHandler`实例的指针。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="cc3b5-107">[在]当前<xref:System.AppDomain>的标识符。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="cc3b5-108">[在][验证器标志](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md)值的组合，指示应执行的验证类型。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="cc3b5-109">[在]退出验证之前要允许的最大错误数。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="cc3b5-110">[在]闲置。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="cc3b5-111">[在]要验证的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="cc3b5-112">[在]指向文件缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="cc3b5-113">[在]要验证的文件的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc3b5-114">返回值</span><span class="sxs-lookup"><span data-stu-id="cc3b5-114">Return Value</span></span>  
  
|<span data-ttu-id="cc3b5-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cc3b5-115">HRESULT</span></span>|<span data-ttu-id="cc3b5-116">说明</span><span class="sxs-lookup"><span data-stu-id="cc3b5-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cc3b5-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc3b5-117">S_OK</span></span>|<span data-ttu-id="cc3b5-118">`Validate`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="cc3b5-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cc3b5-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cc3b5-120">公共语言运行时 （CLR） 尚未加载到进程中，或者 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cc3b5-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cc3b5-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cc3b5-122">呼叫超时。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-122">The call timed out.</span></span>|  
|<span data-ttu-id="cc3b5-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cc3b5-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cc3b5-124">调用方不拥有锁。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cc3b5-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cc3b5-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cc3b5-126">当阻塞的线程或光纤等待事件时，事件已被取消。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cc3b5-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cc3b5-127">E_FAIL</span></span>|<span data-ttu-id="cc3b5-128">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cc3b5-129">当方法返回E_FAIL时，CLR 在进程中不再可用。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cc3b5-130">对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc3b5-131">要求</span><span class="sxs-lookup"><span data-stu-id="cc3b5-131">Requirements</span></span>  
 <span data-ttu-id="cc3b5-132">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc3b5-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc3b5-133">**标题：** I 验证器.idl， I 验证器.h</span><span class="sxs-lookup"><span data-stu-id="cc3b5-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="cc3b5-134">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="cc3b5-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc3b5-135">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc3b5-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc3b5-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc3b5-136">See also</span></span>

- [<span data-ttu-id="cc3b5-137">ICLRValidator 接口</span><span class="sxs-lookup"><span data-stu-id="cc3b5-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
