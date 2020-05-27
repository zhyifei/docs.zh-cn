---
title: IHostTaskManager::SetCLRTaskManager 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetCLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type:
- apiref
ms.openlocfilehash: 0e030a33a0a3368f35c82fad33f1ea2ce32446af
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841823"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="45ecb-102">IHostTaskManager::SetCLRTaskManager 方法</span><span class="sxs-lookup"><span data-stu-id="45ecb-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="45ecb-103">向宿主提供一个接口指针，该指针指向由公共语言运行时（CLR）实现的[ICLRTaskManager](iclrtaskmanager-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="45ecb-103">Provides the host with an interface pointer to an [ICLRTaskManager](iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45ecb-104">语法</span><span class="sxs-lookup"><span data-stu-id="45ecb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45ecb-105">参数</span><span class="sxs-lookup"><span data-stu-id="45ecb-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="45ecb-106">中指向 `ICLRTaskManager` 由公共语言运行时实现的实例的指针。</span><span class="sxs-lookup"><span data-stu-id="45ecb-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45ecb-107">返回值</span><span class="sxs-lookup"><span data-stu-id="45ecb-107">Return Value</span></span>  
  
|<span data-ttu-id="45ecb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="45ecb-108">HRESULT</span></span>|<span data-ttu-id="45ecb-109">说明</span><span class="sxs-lookup"><span data-stu-id="45ecb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="45ecb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="45ecb-110">S_OK</span></span>|<span data-ttu-id="45ecb-111">`SetCLRTaskManager`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="45ecb-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="45ecb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="45ecb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="45ecb-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="45ecb-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="45ecb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="45ecb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="45ecb-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="45ecb-115">The call timed out.</span></span>|  
|<span data-ttu-id="45ecb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="45ecb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="45ecb-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="45ecb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="45ecb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="45ecb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="45ecb-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="45ecb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="45ecb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="45ecb-120">E_FAIL</span></span>|<span data-ttu-id="45ecb-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="45ecb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="45ecb-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="45ecb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="45ecb-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="45ecb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45ecb-124">备注</span><span class="sxs-lookup"><span data-stu-id="45ecb-124">Remarks</span></span>  
 <span data-ttu-id="45ecb-125">运行时调用 `SetCLRTaskManager` 来向宿主提供指向实例的接口指针 `ICLRTaskManager` 。</span><span class="sxs-lookup"><span data-stu-id="45ecb-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45ecb-126">要求</span><span class="sxs-lookup"><span data-stu-id="45ecb-126">Requirements</span></span>  
 <span data-ttu-id="45ecb-127">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="45ecb-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45ecb-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="45ecb-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="45ecb-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="45ecb-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="45ecb-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45ecb-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ecb-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45ecb-131">See also</span></span>

- [<span data-ttu-id="45ecb-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="45ecb-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="45ecb-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="45ecb-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="45ecb-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="45ecb-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="45ecb-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="45ecb-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
