---
title: ICLRMetaHost::RequestRuntimeLoadedNotification 方法
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
ms.openlocfilehash: 23f868bba2dc058d99f1c5c09e9b311b1ff3634a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140902"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="09b99-102">ICLRMetaHost::RequestRuntimeLoadedNotification 方法</span><span class="sxs-lookup"><span data-stu-id="09b99-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="09b99-103">提供一个回调函数，保证在第一次加载公共语言运行时（CLR）版本时，但尚未启动。</span><span class="sxs-lookup"><span data-stu-id="09b99-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="09b99-104">此方法取代了[LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="09b99-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09b99-105">语法</span><span class="sxs-lookup"><span data-stu-id="09b99-105">Syntax</span></span>  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09b99-106">参数</span><span class="sxs-lookup"><span data-stu-id="09b99-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="09b99-107">中已加载新的运行时调用的回调函数。</span><span class="sxs-lookup"><span data-stu-id="09b99-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09b99-108">返回值</span><span class="sxs-lookup"><span data-stu-id="09b99-108">Return Value</span></span>  
 <span data-ttu-id="09b99-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="09b99-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="09b99-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09b99-110">HRESULT</span></span>|<span data-ttu-id="09b99-111">描述</span><span class="sxs-lookup"><span data-stu-id="09b99-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09b99-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="09b99-112">S_OK</span></span>|<span data-ttu-id="09b99-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="09b99-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="09b99-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="09b99-114">E_POINTER</span></span>|<span data-ttu-id="09b99-115">`pCallbackFunction` 为 null。</span><span class="sxs-lookup"><span data-stu-id="09b99-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09b99-116">备注</span><span class="sxs-lookup"><span data-stu-id="09b99-116">Remarks</span></span>  
 <span data-ttu-id="09b99-117">回调的工作方式如下：</span><span class="sxs-lookup"><span data-stu-id="09b99-117">The callback works in the following way:</span></span>  
  
- <span data-ttu-id="09b99-118">只有首次加载运行时才会调用回调。</span><span class="sxs-lookup"><span data-stu-id="09b99-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
- <span data-ttu-id="09b99-119">对于同一运行时的可重入加载，不调用回调。</span><span class="sxs-lookup"><span data-stu-id="09b99-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
- <span data-ttu-id="09b99-120">对于非重入的运行时加载，对回调函数的调用将进行序列化。</span><span class="sxs-lookup"><span data-stu-id="09b99-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="09b99-121">回调函数具有以下原型：</span><span class="sxs-lookup"><span data-stu-id="09b99-121">The callback function has the following prototype:</span></span>  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="09b99-122">回调函数的原型如下所示：</span><span class="sxs-lookup"><span data-stu-id="09b99-122">The callback function prototypes are as follows:</span></span>  
  
- <span data-ttu-id="09b99-123">`pfnCallbackThreadSet`：</span><span class="sxs-lookup"><span data-stu-id="09b99-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- <span data-ttu-id="09b99-124">`pfnCallbackThreadUnset`：</span><span class="sxs-lookup"><span data-stu-id="09b99-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="09b99-125">如果宿主打算加载或导致以重入方式加载另一个运行时，则必须按以下方式使用回调函数中提供的 `pfnCallbackThreadSet` 和 `pfnCallbackThreadUnset` 参数：</span><span class="sxs-lookup"><span data-stu-id="09b99-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
- <span data-ttu-id="09b99-126">在尝试执行此类加载之前，必须由可能导致运行时加载的线程调用 `pfnCallbackThreadSet`。</span><span class="sxs-lookup"><span data-stu-id="09b99-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
- <span data-ttu-id="09b99-127">当线程不再导致此类运行时加载（以及从初始回调返回之前），必须调用 `pfnCallbackThreadUnset`。</span><span class="sxs-lookup"><span data-stu-id="09b99-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
- <span data-ttu-id="09b99-128">`pfnCallbackThreadSet` 和 `pfnCallbackThreadUnset` 都是不可重入的。</span><span class="sxs-lookup"><span data-stu-id="09b99-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="09b99-129">主机应用程序不得调用 `pCallbackFunction` 参数范围之外的 `pfnCallbackThreadSet` 和 `pfnCallbackThreadUnset`。</span><span class="sxs-lookup"><span data-stu-id="09b99-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09b99-130">要求</span><span class="sxs-lookup"><span data-stu-id="09b99-130">Requirements</span></span>  
 <span data-ttu-id="09b99-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="09b99-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09b99-132">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="09b99-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="09b99-133">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="09b99-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09b99-134">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09b99-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09b99-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="09b99-135">See also</span></span>

- [<span data-ttu-id="09b99-136">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="09b99-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="09b99-137">承载</span><span class="sxs-lookup"><span data-stu-id="09b99-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
