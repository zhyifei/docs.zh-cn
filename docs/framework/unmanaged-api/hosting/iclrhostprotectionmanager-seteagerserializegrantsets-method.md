---
title: ICLRHostProtectionManager::SetEagerSerializeGrantSets 方法
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetEagerSerializeGrantSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetEagerSerializeGrantSets
helpviewer_keywords:
- SetEagerSerializeGrantSets method [.NET Framework hosting]
- ICLRHostProtectionManager::SetEagerSerializeGrantSets method [.NET Framework hosting]
ms.assetid: d6158360-22b1-4ace-ad85-d830b9964783
topic_type:
- apiref
ms.openlocfilehash: e911a8e73020321511da5bd7f3ade677058048e4
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703832"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="3b922-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets 方法</span><span class="sxs-lookup"><span data-stu-id="3b922-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="3b922-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="3b922-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b922-104">语法</span><span class="sxs-lookup"><span data-stu-id="3b922-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3b922-105">返回值</span><span class="sxs-lookup"><span data-stu-id="3b922-105">Return Value</span></span>  
  
|<span data-ttu-id="3b922-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3b922-106">HRESULT</span></span>|<span data-ttu-id="3b922-107">说明</span><span class="sxs-lookup"><span data-stu-id="3b922-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3b922-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3b922-108">S_OK</span></span>|<span data-ttu-id="3b922-109">`SetEagerSerializeGrantSets`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="3b922-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="3b922-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3b922-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3b922-111">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="3b922-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3b922-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3b922-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3b922-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="3b922-113">The call timed out.</span></span>|  
|<span data-ttu-id="3b922-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3b922-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3b922-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="3b922-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3b922-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3b922-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3b922-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="3b922-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3b922-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3b922-118">E_FAIL</span></span>|<span data-ttu-id="3b922-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="3b922-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3b922-120">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="3b922-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3b922-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="3b922-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b922-122">要求</span><span class="sxs-lookup"><span data-stu-id="3b922-122">Requirements</span></span>  
 <span data-ttu-id="3b922-123">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3b922-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b922-124">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3b922-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3b922-125">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="3b922-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b922-126">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b922-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b922-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b922-127">See also</span></span>

- [<span data-ttu-id="3b922-128">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="3b922-128">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="3b922-129">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="3b922-129">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
