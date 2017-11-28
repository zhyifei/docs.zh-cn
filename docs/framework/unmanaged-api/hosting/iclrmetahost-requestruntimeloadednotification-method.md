---
title: "ICLRMetaHost::RequestRuntimeLoadedNotification 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.RequestRuntimeLoadedNotification
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 32eb92263685bc3be9f0c28dea88ecfa78c2b52c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="29cf9-102">ICLRMetaHost::RequestRuntimeLoadedNotification 方法</span><span class="sxs-lookup"><span data-stu-id="29cf9-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="29cf9-103">提供保证在首次加载，但尚未启动的公共语言运行时 (CLR) 版本时要调用的回调函数。</span><span class="sxs-lookup"><span data-stu-id="29cf9-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="29cf9-104">此方法取代[LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="29cf9-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29cf9-105">语法</span><span class="sxs-lookup"><span data-stu-id="29cf9-105">Syntax</span></span>  
  
```  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="29cf9-106">参数</span><span class="sxs-lookup"><span data-stu-id="29cf9-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="29cf9-107">[in]当加载新的运行时调用的回调函数。</span><span class="sxs-lookup"><span data-stu-id="29cf9-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29cf9-108">返回值</span><span class="sxs-lookup"><span data-stu-id="29cf9-108">Return Value</span></span>  
 <span data-ttu-id="29cf9-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="29cf9-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="29cf9-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="29cf9-110">HRESULT</span></span>|<span data-ttu-id="29cf9-111">描述</span><span class="sxs-lookup"><span data-stu-id="29cf9-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="29cf9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="29cf9-112">S_OK</span></span>|<span data-ttu-id="29cf9-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="29cf9-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="29cf9-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="29cf9-114">E_POINTER</span></span>|<span data-ttu-id="29cf9-115">`pCallbackFunction` 为 null。</span><span class="sxs-lookup"><span data-stu-id="29cf9-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29cf9-116">备注</span><span class="sxs-lookup"><span data-stu-id="29cf9-116">Remarks</span></span>  
 <span data-ttu-id="29cf9-117">回调的工作方式如下：</span><span class="sxs-lookup"><span data-stu-id="29cf9-117">The callback works in the following way:</span></span>  
  
-   <span data-ttu-id="29cf9-118">仅当首次加载运行时，将调用回调。</span><span class="sxs-lookup"><span data-stu-id="29cf9-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
-   <span data-ttu-id="29cf9-119">对同一个运行时的可重入负载不调用该回调。</span><span class="sxs-lookup"><span data-stu-id="29cf9-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
-   <span data-ttu-id="29cf9-120">来进行非可重入运行时加载，序列化对回调函数的调用。</span><span class="sxs-lookup"><span data-stu-id="29cf9-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="29cf9-121">回调函数具有以下原型：</span><span class="sxs-lookup"><span data-stu-id="29cf9-121">The callback function has the following prototype:</span></span>  
  
```  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="29cf9-122">回调函数的原型如下所示：</span><span class="sxs-lookup"><span data-stu-id="29cf9-122">The callback function prototypes are as follows:</span></span>  
  
-   <span data-ttu-id="29cf9-123">`pfnCallbackThreadSet`：</span><span class="sxs-lookup"><span data-stu-id="29cf9-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
-   <span data-ttu-id="29cf9-124">`pfnCallbackThreadUnset`：</span><span class="sxs-lookup"><span data-stu-id="29cf9-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="29cf9-125">如果宿主要加载或导致另一个运行时，才能加载到可重入的方式，`pfnCallbackThreadSet`和`pfnCallbackThreadUnset`提供在回调必须按以下方式使用函数的参数：</span><span class="sxs-lookup"><span data-stu-id="29cf9-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
-   <span data-ttu-id="29cf9-126">`pfnCallbackThreadSet`必须由尝试此类负载之前，可能会导致运行时负载的线程调用。</span><span class="sxs-lookup"><span data-stu-id="29cf9-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
-   <span data-ttu-id="29cf9-127">`pfnCallbackThreadUnset`必须调用时该线程将不再导致出现运行时负载 （和从初始回调返回之前）。</span><span class="sxs-lookup"><span data-stu-id="29cf9-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
-   <span data-ttu-id="29cf9-128">`pfnCallbackThreadSet`和`pfnCallbackThreadUnset`都是不可重入。</span><span class="sxs-lookup"><span data-stu-id="29cf9-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29cf9-129">主机应用程序不能调用`pfnCallbackThreadSet`和`pfnCallbackThreadUnset`的范围之外`pCallbackFunction`参数。</span><span class="sxs-lookup"><span data-stu-id="29cf9-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29cf9-130">要求</span><span class="sxs-lookup"><span data-stu-id="29cf9-130">Requirements</span></span>  
 <span data-ttu-id="29cf9-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="29cf9-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29cf9-132">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="29cf9-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="29cf9-133">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="29cf9-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29cf9-134">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29cf9-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29cf9-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29cf9-135">See Also</span></span>  
 [<span data-ttu-id="29cf9-136">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="29cf9-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="29cf9-137">承载</span><span class="sxs-lookup"><span data-stu-id="29cf9-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
