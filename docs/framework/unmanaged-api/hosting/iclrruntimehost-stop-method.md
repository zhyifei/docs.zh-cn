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
ms.openlocfilehash: 8d479e271c2cc4ebf9ea6ff349fd28bff37c3857
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436093"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="a4d90-102">ICLRRuntimeHost::Stop 方法</span><span class="sxs-lookup"><span data-stu-id="a4d90-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="a4d90-103">通过公共语言运行时 (CLR) 来停止执行的代码。</span><span class="sxs-lookup"><span data-stu-id="a4d90-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a4d90-104">此方法不释放到主机的资源、 卸载应用程序域，或破坏线程。</span><span class="sxs-lookup"><span data-stu-id="a4d90-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="a4d90-105">必须终止该进程以释放这些资源。</span><span class="sxs-lookup"><span data-stu-id="a4d90-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4d90-106">语法</span><span class="sxs-lookup"><span data-stu-id="a4d90-106">Syntax</span></span>  
  
```  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a4d90-107">返回值</span><span class="sxs-lookup"><span data-stu-id="a4d90-107">Return Value</span></span>  
  
|<span data-ttu-id="a4d90-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a4d90-108">HRESULT</span></span>|<span data-ttu-id="a4d90-109">描述</span><span class="sxs-lookup"><span data-stu-id="a4d90-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a4d90-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4d90-110">S_OK</span></span>|<span data-ttu-id="a4d90-111">`Stop` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="a4d90-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="a4d90-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a4d90-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a4d90-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="a4d90-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a4d90-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a4d90-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a4d90-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="a4d90-115">The call timed out.</span></span>|  
|<span data-ttu-id="a4d90-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a4d90-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a4d90-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="a4d90-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a4d90-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a4d90-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a4d90-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="a4d90-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a4d90-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a4d90-120">E_FAIL</span></span>|<span data-ttu-id="a4d90-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="a4d90-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a4d90-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="a4d90-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a4d90-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="a4d90-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a4d90-124">要求</span><span class="sxs-lookup"><span data-stu-id="a4d90-124">Requirements</span></span>  
 <span data-ttu-id="a4d90-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a4d90-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4d90-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a4d90-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4d90-127">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a4d90-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4d90-128">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4d90-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d90-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4d90-129">See Also</span></span>  
 [<span data-ttu-id="a4d90-130">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="a4d90-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
