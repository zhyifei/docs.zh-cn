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
ms.openlocfilehash: 55cd444ffedc92ba74239421ae548ffd930e6ab7
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703930"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="15893-102">ICLRRuntimeHost::Stop 方法</span><span class="sxs-lookup"><span data-stu-id="15893-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="15893-103">停止由公共语言运行时（CLR）执行的代码。</span><span class="sxs-lookup"><span data-stu-id="15893-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="15893-104">此方法不会向主机释放资源、卸载应用程序域或销毁线程。</span><span class="sxs-lookup"><span data-stu-id="15893-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="15893-105">必须终止进程才能释放这些资源。</span><span class="sxs-lookup"><span data-stu-id="15893-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15893-106">语法</span><span class="sxs-lookup"><span data-stu-id="15893-106">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="15893-107">返回值</span><span class="sxs-lookup"><span data-stu-id="15893-107">Return Value</span></span>  
  
|<span data-ttu-id="15893-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="15893-108">HRESULT</span></span>|<span data-ttu-id="15893-109">说明</span><span class="sxs-lookup"><span data-stu-id="15893-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15893-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="15893-110">S_OK</span></span>|<span data-ttu-id="15893-111">`Stop`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="15893-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="15893-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="15893-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="15893-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="15893-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="15893-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="15893-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="15893-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="15893-115">The call timed out.</span></span>|  
|<span data-ttu-id="15893-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="15893-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="15893-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="15893-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="15893-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="15893-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="15893-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="15893-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="15893-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="15893-120">E_FAIL</span></span>|<span data-ttu-id="15893-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="15893-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="15893-122">如果方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="15893-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="15893-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="15893-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15893-124">要求</span><span class="sxs-lookup"><span data-stu-id="15893-124">Requirements</span></span>  
 <span data-ttu-id="15893-125">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="15893-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15893-126">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="15893-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15893-127">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="15893-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15893-128">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15893-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15893-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15893-129">See also</span></span>

- [<span data-ttu-id="15893-130">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="15893-130">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
