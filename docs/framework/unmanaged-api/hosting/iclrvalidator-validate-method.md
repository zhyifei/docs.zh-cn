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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 559c265c70c199e64782ba185d4925d293d6a778
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158686"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="13087-102">ICLRValidator::Validate 方法</span><span class="sxs-lookup"><span data-stu-id="13087-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="13087-103">验证的可移植可执行 (PE) 或 Microsoft 中间语言 (MSIL) 中指定的文件。</span><span class="sxs-lookup"><span data-stu-id="13087-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13087-104">语法</span><span class="sxs-lookup"><span data-stu-id="13087-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="13087-105">参数</span><span class="sxs-lookup"><span data-stu-id="13087-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="13087-106">[in]一个指向`IVEHandler`处理验证错误的实例。</span><span class="sxs-lookup"><span data-stu-id="13087-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="13087-107">[in]当前标识符<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="13087-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="13087-108">[in]组合[ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md)值，指示应执行的验证类型。</span><span class="sxs-lookup"><span data-stu-id="13087-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="13087-109">[in]最大允许在退出验证之前的错误数。</span><span class="sxs-lookup"><span data-stu-id="13087-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="13087-110">[in]未使用。</span><span class="sxs-lookup"><span data-stu-id="13087-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="13087-111">[in]要验证的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="13087-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="13087-112">[in]指向文件缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="13087-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="13087-113">[in]以字节为单位，要验证的文件的大小。</span><span class="sxs-lookup"><span data-stu-id="13087-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13087-114">返回值</span><span class="sxs-lookup"><span data-stu-id="13087-114">Return Value</span></span>  
  
|<span data-ttu-id="13087-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="13087-115">HRESULT</span></span>|<span data-ttu-id="13087-116">描述</span><span class="sxs-lookup"><span data-stu-id="13087-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="13087-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="13087-117">S_OK</span></span>|<span data-ttu-id="13087-118">`Validate` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="13087-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="13087-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="13087-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="13087-120">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="13087-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="13087-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="13087-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="13087-122">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="13087-122">The call timed out.</span></span>|  
|<span data-ttu-id="13087-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="13087-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="13087-124">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="13087-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="13087-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="13087-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="13087-126">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="13087-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="13087-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="13087-127">E_FAIL</span></span>|<span data-ttu-id="13087-128">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="13087-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="13087-129">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="13087-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="13087-130">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="13087-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13087-131">要求</span><span class="sxs-lookup"><span data-stu-id="13087-131">Requirements</span></span>  
 <span data-ttu-id="13087-132">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="13087-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13087-133">**标头：** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="13087-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="13087-134">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="13087-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13087-135">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13087-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13087-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="13087-136">See also</span></span>

- [<span data-ttu-id="13087-137">ICLRValidator 接口</span><span class="sxs-lookup"><span data-stu-id="13087-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
