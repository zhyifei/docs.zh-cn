---
title: ICLRRuntimeHost::Start 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Start
helpviewer_keywords:
- ICLRRuntimeHost::Start method [.NET Framework hosting]
- Start method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: c0a6dce5-0a8d-42e8-808b-6ca14df9d289
topic_type:
- apiref
ms.openlocfilehash: e5ed1cbb640e760d75e1722871453a0bec283bde
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703913"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="64310-102">ICLRRuntimeHost::Start 方法</span><span class="sxs-lookup"><span data-stu-id="64310-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="64310-103">将公共语言运行时（CLR）初始化为进程。</span><span class="sxs-lookup"><span data-stu-id="64310-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64310-104">语法</span><span class="sxs-lookup"><span data-stu-id="64310-104">Syntax</span></span>  
  
```cpp  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="64310-105">返回值</span><span class="sxs-lookup"><span data-stu-id="64310-105">Return Value</span></span>  
  
|<span data-ttu-id="64310-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64310-106">HRESULT</span></span>|<span data-ttu-id="64310-107">说明</span><span class="sxs-lookup"><span data-stu-id="64310-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="64310-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="64310-108">S_OK</span></span>|<span data-ttu-id="64310-109">`Start`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="64310-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="64310-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="64310-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="64310-111">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="64310-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="64310-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="64310-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="64310-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="64310-113">The call timed out.</span></span>|  
|<span data-ttu-id="64310-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="64310-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="64310-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="64310-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="64310-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="64310-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="64310-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="64310-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="64310-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="64310-118">E_FAIL</span></span>|<span data-ttu-id="64310-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="64310-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="64310-120">如果方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="64310-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="64310-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="64310-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64310-122">备注</span><span class="sxs-lookup"><span data-stu-id="64310-122">Remarks</span></span>  
 <span data-ttu-id="64310-123">在许多情况下，不需要调用 `Start` ，因为运行时将在首次运行托管代码请求时自动初始化自身。</span><span class="sxs-lookup"><span data-stu-id="64310-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="64310-124">但是，可以使用 `Start` 来准确指定运行时应初始化的时间。</span><span class="sxs-lookup"><span data-stu-id="64310-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64310-125">要求</span><span class="sxs-lookup"><span data-stu-id="64310-125">Requirements</span></span>  
 <span data-ttu-id="64310-126">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="64310-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64310-127">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="64310-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64310-128">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="64310-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64310-129">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64310-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64310-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64310-130">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="64310-131">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="64310-131">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
