---
title: ICorRuntimeHost::Stop 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c59a0c5ef1e89c2853a566bd3b587d15a1ed80c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119257"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="d0c21-102">ICorRuntimeHost::Stop 方法</span><span class="sxs-lookup"><span data-stu-id="d0c21-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="d0c21-103">停止执行当前进程的运行时中的代码。</span><span class="sxs-lookup"><span data-stu-id="d0c21-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0c21-104">语法</span><span class="sxs-lookup"><span data-stu-id="d0c21-104">Syntax</span></span>  
  
```  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d0c21-105">返回值</span><span class="sxs-lookup"><span data-stu-id="d0c21-105">Return Value</span></span>  
  
|<span data-ttu-id="d0c21-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d0c21-106">HRESULT</span></span>|<span data-ttu-id="d0c21-107">描述</span><span class="sxs-lookup"><span data-stu-id="d0c21-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d0c21-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d0c21-108">S_OK</span></span>|<span data-ttu-id="d0c21-109">操作成功。</span><span class="sxs-lookup"><span data-stu-id="d0c21-109">The operation was successful.</span></span>|  
|<span data-ttu-id="d0c21-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d0c21-110">S_FALSE</span></span>|<span data-ttu-id="d0c21-111">该操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="d0c21-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="d0c21-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d0c21-112">E_FAIL</span></span>|<span data-ttu-id="d0c21-113">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d0c21-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="d0c21-114">如果方法返回 E_FAIL，公共语言运行时 (CLR) 不再可在该过程中使用。</span><span class="sxs-lookup"><span data-stu-id="d0c21-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="d0c21-115">对任何托管 Api 的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d0c21-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d0c21-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d0c21-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d0c21-117">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d0c21-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0c21-118">备注</span><span class="sxs-lookup"><span data-stu-id="d0c21-118">Remarks</span></span>  
 <span data-ttu-id="d0c21-119">通常不需要调用`Stop`方法，因为该代码将停止执行时在进程退出。</span><span class="sxs-lookup"><span data-stu-id="d0c21-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0c21-120">在调用`Stop`，CLR 不能重新初始化到同一进程。</span><span class="sxs-lookup"><span data-stu-id="d0c21-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0c21-121">要求</span><span class="sxs-lookup"><span data-stu-id="d0c21-121">Requirements</span></span>  
 <span data-ttu-id="d0c21-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d0c21-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0c21-123">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d0c21-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d0c21-124">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d0c21-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d0c21-125">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="d0c21-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0c21-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0c21-126">See also</span></span>

- [<span data-ttu-id="d0c21-127">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="d0c21-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
