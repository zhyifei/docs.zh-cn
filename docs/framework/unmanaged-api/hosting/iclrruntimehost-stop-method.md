---
title: ICLRRuntimeHost::Stop 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85116244ad21842fab025ddd48106deef75f210b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166965"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="857b7-102">ICLRRuntimeHost::Stop 方法</span><span class="sxs-lookup"><span data-stu-id="857b7-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="857b7-103">公共语言运行时 (CLR) 将停止执行代码。</span><span class="sxs-lookup"><span data-stu-id="857b7-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="857b7-104">此方法不释放给主机的资源、 卸载应用程序域或销毁线程。</span><span class="sxs-lookup"><span data-stu-id="857b7-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="857b7-105">必须终止该进程以释放这些资源。</span><span class="sxs-lookup"><span data-stu-id="857b7-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="857b7-106">语法</span><span class="sxs-lookup"><span data-stu-id="857b7-106">Syntax</span></span>  
  
```  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="857b7-107">返回值</span><span class="sxs-lookup"><span data-stu-id="857b7-107">Return Value</span></span>  
  
|<span data-ttu-id="857b7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="857b7-108">HRESULT</span></span>|<span data-ttu-id="857b7-109">描述</span><span class="sxs-lookup"><span data-stu-id="857b7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="857b7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="857b7-110">S_OK</span></span>|<span data-ttu-id="857b7-111">`Stop` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="857b7-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="857b7-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="857b7-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="857b7-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="857b7-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="857b7-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="857b7-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="857b7-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="857b7-115">The call timed out.</span></span>|  
|<span data-ttu-id="857b7-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="857b7-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="857b7-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="857b7-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="857b7-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="857b7-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="857b7-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="857b7-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="857b7-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="857b7-120">E_FAIL</span></span>|<span data-ttu-id="857b7-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="857b7-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="857b7-122">如果方法返回 E_FAIL，CLR 不再在该过程中可用。</span><span class="sxs-lookup"><span data-stu-id="857b7-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="857b7-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="857b7-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="857b7-124">要求</span><span class="sxs-lookup"><span data-stu-id="857b7-124">Requirements</span></span>  
 <span data-ttu-id="857b7-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="857b7-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="857b7-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="857b7-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="857b7-127">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="857b7-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="857b7-128">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="857b7-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="857b7-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="857b7-129">See also</span></span>

- [<span data-ttu-id="857b7-130">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="857b7-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
