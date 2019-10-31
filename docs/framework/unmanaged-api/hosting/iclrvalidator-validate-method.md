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
ms.openlocfilehash: 497a115b980bb58a3906fda68d7ff564efe78089
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127827"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="c1d91-102">ICLRValidator::Validate 方法</span><span class="sxs-lookup"><span data-stu-id="c1d91-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="c1d91-103">验证指定文件中的可移植可执行（PE）或 Microsoft 中间语言（MSIL）。</span><span class="sxs-lookup"><span data-stu-id="c1d91-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1d91-104">语法</span><span class="sxs-lookup"><span data-stu-id="c1d91-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c1d91-105">参数</span><span class="sxs-lookup"><span data-stu-id="c1d91-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="c1d91-106">中指向处理验证错误的 `IVEHandler` 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="c1d91-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="c1d91-107">中当前 <xref:System.AppDomain>的标识符。</span><span class="sxs-lookup"><span data-stu-id="c1d91-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="c1d91-108">中[ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md)值的组合，用于指示应执行的验证类型。</span><span class="sxs-lookup"><span data-stu-id="c1d91-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="c1d91-109">中在退出验证之前允许的最大错误数。</span><span class="sxs-lookup"><span data-stu-id="c1d91-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="c1d91-110">中用.</span><span class="sxs-lookup"><span data-stu-id="c1d91-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="c1d91-111">中要验证的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="c1d91-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="c1d91-112">中指向文件缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="c1d91-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="c1d91-113">中要验证的文件的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="c1d91-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1d91-114">返回值</span><span class="sxs-lookup"><span data-stu-id="c1d91-114">Return Value</span></span>  
  
|<span data-ttu-id="c1d91-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c1d91-115">HRESULT</span></span>|<span data-ttu-id="c1d91-116">描述</span><span class="sxs-lookup"><span data-stu-id="c1d91-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c1d91-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="c1d91-117">S_OK</span></span>|<span data-ttu-id="c1d91-118">`Validate` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="c1d91-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="c1d91-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c1d91-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c1d91-120">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c1d91-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c1d91-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c1d91-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c1d91-122">调用超时。</span><span class="sxs-lookup"><span data-stu-id="c1d91-122">The call timed out.</span></span>|  
|<span data-ttu-id="c1d91-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c1d91-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c1d91-124">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c1d91-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c1d91-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c1d91-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c1d91-126">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="c1d91-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c1d91-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c1d91-127">E_FAIL</span></span>|<span data-ttu-id="c1d91-128">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c1d91-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c1d91-129">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="c1d91-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c1d91-130">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c1d91-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c1d91-131">要求</span><span class="sxs-lookup"><span data-stu-id="c1d91-131">Requirements</span></span>  
 <span data-ttu-id="c1d91-132">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c1d91-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1d91-133">**标头：** IValidator，IValidator</span><span class="sxs-lookup"><span data-stu-id="c1d91-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="c1d91-134">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c1d91-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1d91-135">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1d91-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1d91-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1d91-136">See also</span></span>

- [<span data-ttu-id="c1d91-137">ICLRValidator 接口</span><span class="sxs-lookup"><span data-stu-id="c1d91-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
