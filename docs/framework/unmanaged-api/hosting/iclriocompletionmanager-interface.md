---
title: "ICLRIoCompletionManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 99dc183674abaff33047f070c14794150a8615f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="f6be6-102">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="f6be6-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="f6be6-103">实现一个回调方法，指定的 I/O 的状态以便通知公共语言运行时 (CLR) 主机请求。</span><span class="sxs-lookup"><span data-stu-id="f6be6-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f6be6-104">方法</span><span class="sxs-lookup"><span data-stu-id="f6be6-104">Methods</span></span>  
  
|<span data-ttu-id="f6be6-105">方法</span><span class="sxs-lookup"><span data-stu-id="f6be6-105">Method</span></span>|<span data-ttu-id="f6be6-106">描述</span><span class="sxs-lookup"><span data-stu-id="f6be6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f6be6-107">OnComplete 方法</span><span class="sxs-lookup"><span data-stu-id="f6be6-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="f6be6-108">通知由调用的 I/O 请求的状态的 CLR [ihostiocompletionmanager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f6be6-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6be6-109">备注</span><span class="sxs-lookup"><span data-stu-id="f6be6-109">Remarks</span></span>  
 <span data-ttu-id="f6be6-110">主机通过使用实现的 I/O 完成抽象[IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="f6be6-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="f6be6-111">CLR 通过此接口，使输入/输出请求和主机通知此类请求的结果的运行时通过使用`ICLRIoCompletionManager`接口。</span><span class="sxs-lookup"><span data-stu-id="f6be6-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6be6-112">惠?</span><span class="sxs-lookup"><span data-stu-id="f6be6-112">Requirements</span></span>  
 <span data-ttu-id="f6be6-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f6be6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6be6-114">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f6be6-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f6be6-115">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f6be6-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6be6-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6be6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6be6-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6be6-117">See Also</span></span>  
 [<span data-ttu-id="f6be6-118">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="f6be6-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="f6be6-119">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="f6be6-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 [<span data-ttu-id="f6be6-120">承载接口</span><span class="sxs-lookup"><span data-stu-id="f6be6-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
