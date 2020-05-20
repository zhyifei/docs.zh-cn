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
ms.openlocfilehash: 822b51531b7afc1c824c74b9580d9208e347e13b
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703561"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="6dec1-102">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="6dec1-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="6dec1-103">实现一个回调方法，该方法允许宿主向公共语言运行时（CLR）通知指定 i/o 请求的状态。</span><span class="sxs-lookup"><span data-stu-id="6dec1-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6dec1-104">方法</span><span class="sxs-lookup"><span data-stu-id="6dec1-104">Methods</span></span>  
  
|<span data-ttu-id="6dec1-105">方法</span><span class="sxs-lookup"><span data-stu-id="6dec1-105">Method</span></span>|<span data-ttu-id="6dec1-106">说明</span><span class="sxs-lookup"><span data-stu-id="6dec1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6dec1-107">OnComplete 方法</span><span class="sxs-lookup"><span data-stu-id="6dec1-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="6dec1-108">使用对[IHostIoCompletionManager：： Bind](ihostiocompletionmanager-bind-method.md)方法的调用，将发出的 i/o 请求状态通知给 CLR。</span><span class="sxs-lookup"><span data-stu-id="6dec1-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6dec1-109">备注</span><span class="sxs-lookup"><span data-stu-id="6dec1-109">Remarks</span></span>  
 <span data-ttu-id="6dec1-110">宿主通过使用[IHostIoCompletionManager](ihostiocompletionmanager-interface.md)接口实现 i/o 完成抽象。</span><span class="sxs-lookup"><span data-stu-id="6dec1-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="6dec1-111">CLR 通过此接口发出 i/o 请求，主机使用接口通知运行时此类请求的结果 `ICLRIoCompletionManager` 。</span><span class="sxs-lookup"><span data-stu-id="6dec1-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dec1-112">要求</span><span class="sxs-lookup"><span data-stu-id="6dec1-112">Requirements</span></span>  
 <span data-ttu-id="6dec1-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6dec1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dec1-114">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6dec1-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6dec1-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="6dec1-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6dec1-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dec1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dec1-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6dec1-117">See also</span></span>

- [<span data-ttu-id="6dec1-118">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="6dec1-118">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="6dec1-119">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="6dec1-119">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="6dec1-120">承载接口</span><span class="sxs-lookup"><span data-stu-id="6dec1-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
