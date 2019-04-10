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
ms.openlocfilehash: 91bb1a9416e577dbb5cc96e8be87033c53232811
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336689"
---
# <a name="lockclrversion-function"></a><span data-ttu-id="999ca-102">LockClrVersion 函数</span><span class="sxs-lookup"><span data-stu-id="999ca-102">LockClrVersion Function</span></span>
<span data-ttu-id="999ca-103">允许宿主确定在进行显式初始化 CLR 之前将在进程中使用的公共语言运行时 (CLR) 的版本。</span><span class="sxs-lookup"><span data-stu-id="999ca-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="999ca-104">此函数中不推荐[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="999ca-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="999ca-105">语法</span><span class="sxs-lookup"><span data-stu-id="999ca-105">Syntax</span></span>  
  
```  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="999ca-106">参数</span><span class="sxs-lookup"><span data-stu-id="999ca-106">Parameters</span></span>  
 `hostCallback`  
 <span data-ttu-id="999ca-107">[in]要由 CLR 初始化时调用的函数。</span><span class="sxs-lookup"><span data-stu-id="999ca-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="999ca-108">[in]正在启动的初始化由主机以通知 CLR 调用的函数。</span><span class="sxs-lookup"><span data-stu-id="999ca-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="999ca-109">[in]函数将调用的主机，告知 CLR 初始化已完成。</span><span class="sxs-lookup"><span data-stu-id="999ca-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="999ca-110">返回值</span><span class="sxs-lookup"><span data-stu-id="999ca-110">Return Value</span></span>  
 <span data-ttu-id="999ca-111">此方法返回标准 COM 错误代码，定义在 WinError.h，除了以下值。</span><span class="sxs-lookup"><span data-stu-id="999ca-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="999ca-112">返回代码</span><span class="sxs-lookup"><span data-stu-id="999ca-112">Return code</span></span>|<span data-ttu-id="999ca-113">描述</span><span class="sxs-lookup"><span data-stu-id="999ca-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="999ca-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="999ca-114">S_OK</span></span>|<span data-ttu-id="999ca-115">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="999ca-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="999ca-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="999ca-116">E_INVALIDARG</span></span>|<span data-ttu-id="999ca-117">一个或多个参数为 null。</span><span class="sxs-lookup"><span data-stu-id="999ca-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="999ca-118">备注</span><span class="sxs-lookup"><span data-stu-id="999ca-118">Remarks</span></span>  
 <span data-ttu-id="999ca-119">在宿主调用`LockClrVersion`之前初始化 CLR。</span><span class="sxs-lookup"><span data-stu-id="999ca-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> `LockClrVersion` <span data-ttu-id="999ca-120">采用三个参数，所有这些都是类型的回调[FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)。</span><span class="sxs-lookup"><span data-stu-id="999ca-120">takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="999ca-121">此类型定义，如下所示。</span><span class="sxs-lookup"><span data-stu-id="999ca-121">This type is defined as follows.</span></span>  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="999ca-122">在运行时初始化时将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="999ca-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1. <span data-ttu-id="999ca-123">在宿主调用[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)或某个其他运行时初始化函数。</span><span class="sxs-lookup"><span data-stu-id="999ca-123">The host calls [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="999ca-124">或者，主机无法初始化运行时使用激活 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="999ca-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2. <span data-ttu-id="999ca-125">运行时调用由指定的函数`hostCallback`参数。</span><span class="sxs-lookup"><span data-stu-id="999ca-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3. <span data-ttu-id="999ca-126">由指定的函数`hostCallback`然后进行以下调用顺序：</span><span class="sxs-lookup"><span data-stu-id="999ca-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    -   <span data-ttu-id="999ca-127">由指定的函数`pBeginHostSetup`参数。</span><span class="sxs-lookup"><span data-stu-id="999ca-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    -   `CorBindToRuntimeEx` <span data-ttu-id="999ca-128">（或另一个运行时初始化函数）。</span><span class="sxs-lookup"><span data-stu-id="999ca-128">(or another runtime initialization function).</span></span>  
  
    -   <span data-ttu-id="999ca-129">[Iclrruntimehost:: Sethostcontrol](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)。</span><span class="sxs-lookup"><span data-stu-id="999ca-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    -   <span data-ttu-id="999ca-130">[Iclrruntimehost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)。</span><span class="sxs-lookup"><span data-stu-id="999ca-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span></span>  
  
    -   <span data-ttu-id="999ca-131">由指定的函数`pEndHostSetup`参数。</span><span class="sxs-lookup"><span data-stu-id="999ca-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="999ca-132">从所有调用`pBeginHostSetup`到`pEndHostSetup`必须出现在单个线程或纤程，具有相同的逻辑堆栈上。</span><span class="sxs-lookup"><span data-stu-id="999ca-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="999ca-133">此线程可以不同于在其线程`hostCallback`调用。</span><span class="sxs-lookup"><span data-stu-id="999ca-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="999ca-134">要求</span><span class="sxs-lookup"><span data-stu-id="999ca-134">Requirements</span></span>  
 <span data-ttu-id="999ca-135">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="999ca-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="999ca-136">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="999ca-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="999ca-137">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="999ca-137">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="999ca-138">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="999ca-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="999ca-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="999ca-139">See also</span></span>

- [<span data-ttu-id="999ca-140">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="999ca-140">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
