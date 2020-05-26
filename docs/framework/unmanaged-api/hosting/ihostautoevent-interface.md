---
title: IHostAutoEvent 接口
ms.date: 03/30/2017
api_name:
- IHostAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent
helpviewer_keywords:
- IHostAutoEvent interface [.NET Framework hosting]
ms.assetid: 6c1d15c1-a80a-4ee9-b1e4-6e859db6575a
topic_type:
- apiref
ms.openlocfilehash: a24939ac0b0808546ef3615fae4909c6c3cf8a2e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804995"
---
# <a name="ihostautoevent-interface"></a><span data-ttu-id="d4601-102">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="d4601-102">IHostAutoEvent Interface</span></span>
<span data-ttu-id="d4601-103">提供宿主自动重置事件的实现的表示形式。</span><span class="sxs-lookup"><span data-stu-id="d4601-103">Provides a representation of the host's implementation of an auto-reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d4601-104">方法</span><span class="sxs-lookup"><span data-stu-id="d4601-104">Methods</span></span>  
  
|<span data-ttu-id="d4601-105">方法</span><span class="sxs-lookup"><span data-stu-id="d4601-105">Method</span></span>|<span data-ttu-id="d4601-106">说明</span><span class="sxs-lookup"><span data-stu-id="d4601-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d4601-107">Set 方法</span><span class="sxs-lookup"><span data-stu-id="d4601-107">Set Method</span></span>](ihostautoevent-set-method.md)|<span data-ttu-id="d4601-108">将当前 `IHostAutoEvent` 实例设置为终止状态。</span><span class="sxs-lookup"><span data-stu-id="d4601-108">Sets the current `IHostAutoEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="d4601-109">Wait 方法</span><span class="sxs-lookup"><span data-stu-id="d4601-109">Wait Method</span></span>](ihostautoevent-wait-method.md)|<span data-ttu-id="d4601-110">导致当前 `IHostAutoEvent` 实例等待，直到事件拥有或经过指定的时间量。</span><span class="sxs-lookup"><span data-stu-id="d4601-110">Causes the current `IHostAutoEvent` instance to wait until the event is owned or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d4601-111">要求</span><span class="sxs-lookup"><span data-stu-id="d4601-111">Requirements</span></span>  
 <span data-ttu-id="d4601-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d4601-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4601-113">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d4601-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d4601-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d4601-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4601-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4601-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4601-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4601-116">See also</span></span>

- [<span data-ttu-id="d4601-117">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="d4601-117">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="d4601-118">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="d4601-118">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="d4601-119">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="d4601-119">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="d4601-120">承载接口</span><span class="sxs-lookup"><span data-stu-id="d4601-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
