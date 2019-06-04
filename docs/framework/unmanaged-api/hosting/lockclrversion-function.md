---
title: LockClrVersion 函数
ms.date: 03/30/2017
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16dd1b895abbd2357c46361c6381b1625422403f
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490183"
---
# <a name="lockclrversion-function"></a><span data-ttu-id="70eac-102">LockClrVersion 函数</span><span class="sxs-lookup"><span data-stu-id="70eac-102">LockClrVersion Function</span></span>
<span data-ttu-id="70eac-103">允许宿主确定在进行显式初始化 CLR 之前将在进程中使用的公共语言运行时 (CLR) 的版本。</span><span class="sxs-lookup"><span data-stu-id="70eac-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="70eac-104">.NET Framework 4 中已弃用此函数。</span><span class="sxs-lookup"><span data-stu-id="70eac-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70eac-105">语法</span><span class="sxs-lookup"><span data-stu-id="70eac-105">Syntax</span></span>  
  
```  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70eac-106">参数</span><span class="sxs-lookup"><span data-stu-id="70eac-106">Parameters</span></span>  
 `hostCallback`  
 <span data-ttu-id="70eac-107">[in]要由 CLR 初始化时调用的函数。</span><span class="sxs-lookup"><span data-stu-id="70eac-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="70eac-108">[in]正在启动的初始化由主机以通知 CLR 调用的函数。</span><span class="sxs-lookup"><span data-stu-id="70eac-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="70eac-109">[in]函数将调用的主机，告知 CLR 初始化已完成。</span><span class="sxs-lookup"><span data-stu-id="70eac-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70eac-110">返回值</span><span class="sxs-lookup"><span data-stu-id="70eac-110">Return Value</span></span>  
 <span data-ttu-id="70eac-111">此方法返回标准 COM 错误代码，定义在 WinError.h，除了以下值。</span><span class="sxs-lookup"><span data-stu-id="70eac-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="70eac-112">返回代码</span><span class="sxs-lookup"><span data-stu-id="70eac-112">Return code</span></span>|<span data-ttu-id="70eac-113">描述</span><span class="sxs-lookup"><span data-stu-id="70eac-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="70eac-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="70eac-114">S_OK</span></span>|<span data-ttu-id="70eac-115">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="70eac-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="70eac-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="70eac-116">E_INVALIDARG</span></span>|<span data-ttu-id="70eac-117">一个或多个参数为 null。</span><span class="sxs-lookup"><span data-stu-id="70eac-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70eac-118">备注</span><span class="sxs-lookup"><span data-stu-id="70eac-118">Remarks</span></span>  
 <span data-ttu-id="70eac-119">在宿主调用`LockClrVersion`之前初始化 CLR。</span><span class="sxs-lookup"><span data-stu-id="70eac-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> <span data-ttu-id="70eac-120">`LockClrVersion` 采用三个参数，所有这些都是类型的回调[FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)。</span><span class="sxs-lookup"><span data-stu-id="70eac-120">`LockClrVersion` takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="70eac-121">此类型定义，如下所示。</span><span class="sxs-lookup"><span data-stu-id="70eac-121">This type is defined as follows.</span></span>  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="70eac-122">在运行时初始化时将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="70eac-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1. <span data-ttu-id="70eac-123">在宿主调用[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)或某个其他运行时初始化函数。</span><span class="sxs-lookup"><span data-stu-id="70eac-123">The host calls [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="70eac-124">或者，主机无法初始化运行时使用激活 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="70eac-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2. <span data-ttu-id="70eac-125">运行时调用由指定的函数`hostCallback`参数。</span><span class="sxs-lookup"><span data-stu-id="70eac-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3. <span data-ttu-id="70eac-126">由指定的函数`hostCallback`然后进行以下调用顺序：</span><span class="sxs-lookup"><span data-stu-id="70eac-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    - <span data-ttu-id="70eac-127">由指定的函数`pBeginHostSetup`参数。</span><span class="sxs-lookup"><span data-stu-id="70eac-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    - <span data-ttu-id="70eac-128">`CorBindToRuntimeEx` （或另一个运行时初始化函数）。</span><span class="sxs-lookup"><span data-stu-id="70eac-128">`CorBindToRuntimeEx` (or another runtime initialization function).</span></span>  
  
    - <span data-ttu-id="70eac-129">[Iclrruntimehost:: Sethostcontrol](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)。</span><span class="sxs-lookup"><span data-stu-id="70eac-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    - <span data-ttu-id="70eac-130">[Iclrruntimehost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)。</span><span class="sxs-lookup"><span data-stu-id="70eac-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span></span>  
  
    - <span data-ttu-id="70eac-131">由指定的函数`pEndHostSetup`参数。</span><span class="sxs-lookup"><span data-stu-id="70eac-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="70eac-132">从所有调用`pBeginHostSetup`到`pEndHostSetup`必须出现在单个线程或纤程，具有相同的逻辑堆栈上。</span><span class="sxs-lookup"><span data-stu-id="70eac-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="70eac-133">此线程可以不同于在其线程`hostCallback`调用。</span><span class="sxs-lookup"><span data-stu-id="70eac-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70eac-134">要求</span><span class="sxs-lookup"><span data-stu-id="70eac-134">Requirements</span></span>  
 <span data-ttu-id="70eac-135">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="70eac-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70eac-136">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="70eac-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="70eac-137">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="70eac-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="70eac-138">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70eac-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70eac-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="70eac-139">See also</span></span>

- [<span data-ttu-id="70eac-140">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="70eac-140">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
