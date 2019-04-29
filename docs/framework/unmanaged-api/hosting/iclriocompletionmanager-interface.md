---
title: ICLRIoCompletionManager 接口
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7864bb81c3b457bf8ec07cd194d24b29a42bd441
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61767463"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="30c49-102">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="30c49-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="30c49-103">实现回调方法，允许宿主以通知公共语言运行时 (CLR) 的状态的指定 I/O 请求。</span><span class="sxs-lookup"><span data-stu-id="30c49-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="30c49-104">方法</span><span class="sxs-lookup"><span data-stu-id="30c49-104">Methods</span></span>  
  
|<span data-ttu-id="30c49-105">方法</span><span class="sxs-lookup"><span data-stu-id="30c49-105">Method</span></span>|<span data-ttu-id="30c49-106">描述</span><span class="sxs-lookup"><span data-stu-id="30c49-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="30c49-107">OnComplete 方法</span><span class="sxs-lookup"><span data-stu-id="30c49-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="30c49-108">通知的状态可能由调用的 I/O 请求的 CLR [ihostiocompletionmanager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="30c49-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30c49-109">备注</span><span class="sxs-lookup"><span data-stu-id="30c49-109">Remarks</span></span>  
 <span data-ttu-id="30c49-110">主机通过使用来实现的 I/O 完成抽象[IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="30c49-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="30c49-111">CLR 发出 I/O 请求通过此接口，并在主机通知此类请求的结果的运行时通过使用`ICLRIoCompletionManager`接口。</span><span class="sxs-lookup"><span data-stu-id="30c49-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30c49-112">要求</span><span class="sxs-lookup"><span data-stu-id="30c49-112">Requirements</span></span>  
 <span data-ttu-id="30c49-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="30c49-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30c49-114">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="30c49-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30c49-115">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="30c49-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30c49-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30c49-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c49-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="30c49-117">See also</span></span>

- [<span data-ttu-id="30c49-118">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="30c49-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="30c49-119">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="30c49-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="30c49-120">承载接口</span><span class="sxs-lookup"><span data-stu-id="30c49-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
