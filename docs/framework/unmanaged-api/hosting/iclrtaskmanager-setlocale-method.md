---
title: ICLRTaskManager::SetLocale 方法
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: ed16bb7f-4206-43a8-b9e9-c5737b69e3af
topic_type:
- apiref
ms.openlocfilehash: 8f316d91aab4c3862a0ad45b41539a4b80791ab9
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762783"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="292bd-102">ICLRTaskManager::SetLocale 方法</span><span class="sxs-lookup"><span data-stu-id="292bd-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="292bd-103">通知公共语言运行时（CLR）宿主已经修改了当前正在执行的任务的区域设置标识符的值（映射到地理区域和语言）。</span><span class="sxs-lookup"><span data-stu-id="292bd-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="292bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="292bd-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="292bd-105">参数</span><span class="sxs-lookup"><span data-stu-id="292bd-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="292bd-106">中映射到新分配的地理区域和语言的区域设置标识符值。</span><span class="sxs-lookup"><span data-stu-id="292bd-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="292bd-107">返回值</span><span class="sxs-lookup"><span data-stu-id="292bd-107">Return Value</span></span>  
  
|<span data-ttu-id="292bd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="292bd-108">HRESULT</span></span>|<span data-ttu-id="292bd-109">说明</span><span class="sxs-lookup"><span data-stu-id="292bd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="292bd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="292bd-110">S_OK</span></span>|<span data-ttu-id="292bd-111">该方法已成功返回。</span><span class="sxs-lookup"><span data-stu-id="292bd-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="292bd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="292bd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="292bd-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="292bd-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="292bd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="292bd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="292bd-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="292bd-115">The call timed out.</span></span>|  
|<span data-ttu-id="292bd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="292bd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="292bd-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="292bd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="292bd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="292bd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="292bd-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="292bd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="292bd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="292bd-120">E_FAIL</span></span>|<span data-ttu-id="292bd-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="292bd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="292bd-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="292bd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="292bd-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="292bd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="292bd-124">注解</span><span class="sxs-lookup"><span data-stu-id="292bd-124">Remarks</span></span>  
 <span data-ttu-id="292bd-125">`SetLocale`使宿主有机会执行它可能对区域设置进行同步的任何机制。</span><span class="sxs-lookup"><span data-stu-id="292bd-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="292bd-126">要求</span><span class="sxs-lookup"><span data-stu-id="292bd-126">Requirements</span></span>  
 <span data-ttu-id="292bd-127">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="292bd-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="292bd-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="292bd-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="292bd-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="292bd-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="292bd-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="292bd-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="292bd-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="292bd-131">See also</span></span>

- [<span data-ttu-id="292bd-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="292bd-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="292bd-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="292bd-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="292bd-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="292bd-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="292bd-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="292bd-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
