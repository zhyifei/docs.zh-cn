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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 160e31859e3d58812861d4462e77d68fa18d6186
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944663"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="4fb8a-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets 方法</span><span class="sxs-lookup"><span data-stu-id="4fb8a-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="4fb8a-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="4fb8a-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fb8a-104">语法</span><span class="sxs-lookup"><span data-stu-id="4fb8a-104">Syntax</span></span>  
  
```  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4fb8a-105">返回值</span><span class="sxs-lookup"><span data-stu-id="4fb8a-105">Return Value</span></span>  
  
|<span data-ttu-id="4fb8a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4fb8a-106">HRESULT</span></span>|<span data-ttu-id="4fb8a-107">描述</span><span class="sxs-lookup"><span data-stu-id="4fb8a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4fb8a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="4fb8a-108">S_OK</span></span>|<span data-ttu-id="4fb8a-109">`SetEagerSerializeGrantSets` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="4fb8a-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="4fb8a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4fb8a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4fb8a-111">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="4fb8a-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4fb8a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4fb8a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4fb8a-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="4fb8a-113">The call timed out.</span></span>|  
|<span data-ttu-id="4fb8a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4fb8a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4fb8a-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="4fb8a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4fb8a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4fb8a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4fb8a-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="4fb8a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4fb8a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4fb8a-118">E_FAIL</span></span>|<span data-ttu-id="4fb8a-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="4fb8a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4fb8a-120">方法返回 E_FAIL 后，CLR 不再在进程中使用。</span><span class="sxs-lookup"><span data-stu-id="4fb8a-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4fb8a-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="4fb8a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4fb8a-122">要求</span><span class="sxs-lookup"><span data-stu-id="4fb8a-122">Requirements</span></span>  
 <span data-ttu-id="4fb8a-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb8a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fb8a-124">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4fb8a-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4fb8a-125">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4fb8a-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4fb8a-126">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fb8a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fb8a-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="4fb8a-127">See also</span></span>

- [<span data-ttu-id="4fb8a-128">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="4fb8a-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="4fb8a-129">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="4fb8a-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
