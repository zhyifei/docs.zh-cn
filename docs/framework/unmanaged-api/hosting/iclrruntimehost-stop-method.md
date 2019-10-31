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
ms.openlocfilehash: 0b59532d18848f1896977aa37f0a9f54a939aa75
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120380"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="adc5c-102">ICLRRuntimeHost::Stop 方法</span><span class="sxs-lookup"><span data-stu-id="adc5c-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="adc5c-103">停止由公共语言运行时（CLR）执行的代码。</span><span class="sxs-lookup"><span data-stu-id="adc5c-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="adc5c-104">此方法不会向主机释放资源、卸载应用程序域或销毁线程。</span><span class="sxs-lookup"><span data-stu-id="adc5c-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="adc5c-105">必须终止进程才能释放这些资源。</span><span class="sxs-lookup"><span data-stu-id="adc5c-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adc5c-106">语法</span><span class="sxs-lookup"><span data-stu-id="adc5c-106">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="adc5c-107">返回值</span><span class="sxs-lookup"><span data-stu-id="adc5c-107">Return Value</span></span>  
  
|<span data-ttu-id="adc5c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="adc5c-108">HRESULT</span></span>|<span data-ttu-id="adc5c-109">描述</span><span class="sxs-lookup"><span data-stu-id="adc5c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="adc5c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="adc5c-110">S_OK</span></span>|<span data-ttu-id="adc5c-111">`Stop` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="adc5c-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="adc5c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="adc5c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="adc5c-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="adc5c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="adc5c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="adc5c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="adc5c-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="adc5c-115">The call timed out.</span></span>|  
|<span data-ttu-id="adc5c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="adc5c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="adc5c-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="adc5c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="adc5c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="adc5c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="adc5c-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="adc5c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="adc5c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="adc5c-120">E_FAIL</span></span>|<span data-ttu-id="adc5c-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="adc5c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="adc5c-122">如果某个方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="adc5c-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="adc5c-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="adc5c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="adc5c-124">要求</span><span class="sxs-lookup"><span data-stu-id="adc5c-124">Requirements</span></span>  
 <span data-ttu-id="adc5c-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="adc5c-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adc5c-126">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="adc5c-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="adc5c-127">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="adc5c-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="adc5c-128">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adc5c-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adc5c-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="adc5c-129">See also</span></span>

- [<span data-ttu-id="adc5c-130">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="adc5c-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
