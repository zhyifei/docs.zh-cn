---
title: "ICLRRuntimeHost::Stop 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.Stop
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3798c4fc451b78257373c0ac47a5e7e7c27dd048
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="27f7a-102">ICLRRuntimeHost::Stop 方法</span><span class="sxs-lookup"><span data-stu-id="27f7a-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="27f7a-103">通过公共语言运行时 (CLR) 来停止执行的代码。</span><span class="sxs-lookup"><span data-stu-id="27f7a-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="27f7a-104">此方法不释放到主机的资源、 卸载应用程序域，或破坏线程。</span><span class="sxs-lookup"><span data-stu-id="27f7a-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="27f7a-105">必须终止该进程以释放这些资源。</span><span class="sxs-lookup"><span data-stu-id="27f7a-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27f7a-106">语法</span><span class="sxs-lookup"><span data-stu-id="27f7a-106">Syntax</span></span>  
  
```  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="27f7a-107">返回值</span><span class="sxs-lookup"><span data-stu-id="27f7a-107">Return Value</span></span>  
  
|<span data-ttu-id="27f7a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27f7a-108">HRESULT</span></span>|<span data-ttu-id="27f7a-109">描述</span><span class="sxs-lookup"><span data-stu-id="27f7a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27f7a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="27f7a-110">S_OK</span></span>|<span data-ttu-id="27f7a-111">`Stop`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="27f7a-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="27f7a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="27f7a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="27f7a-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="27f7a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="27f7a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="27f7a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="27f7a-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="27f7a-115">The call timed out.</span></span>|  
|<span data-ttu-id="27f7a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="27f7a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="27f7a-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="27f7a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="27f7a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="27f7a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="27f7a-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="27f7a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="27f7a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="27f7a-120">E_FAIL</span></span>|<span data-ttu-id="27f7a-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="27f7a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="27f7a-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="27f7a-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="27f7a-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="27f7a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="27f7a-124">要求</span><span class="sxs-lookup"><span data-stu-id="27f7a-124">Requirements</span></span>  
 <span data-ttu-id="27f7a-125">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="27f7a-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27f7a-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="27f7a-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27f7a-127">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="27f7a-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27f7a-128">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27f7a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27f7a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27f7a-129">See Also</span></span>  
 [<span data-ttu-id="27f7a-130">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="27f7a-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
