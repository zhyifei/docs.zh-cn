---
title: "ETaskType 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ETaskType
api_location: mscoree.dll
api_type: COM
f1_keywords: ETaskType
helpviewer_keywords: ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7973b8cbd49858daaf6f08d55c7d9f60f687a72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="b3f95-102">ETaskType 枚举</span><span class="sxs-lookup"><span data-stu-id="b3f95-102">ETaskType Enumeration</span></span>
<span data-ttu-id="b3f95-103">包含值，用于指示表示通过以下任一方法的任务的类型[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)或[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="b3f95-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) or an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3f95-104">语法</span><span class="sxs-lookup"><span data-stu-id="b3f95-104">Syntax</span></span>  
  
```  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a><span data-ttu-id="b3f95-105">成员</span><span class="sxs-lookup"><span data-stu-id="b3f95-105">Members</span></span>  
  
|<span data-ttu-id="b3f95-106">成员</span><span class="sxs-lookup"><span data-stu-id="b3f95-106">Member</span></span>|<span data-ttu-id="b3f95-107">描述</span><span class="sxs-lookup"><span data-stu-id="b3f95-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="b3f95-108">接口表示一个应用程序域卸载任务。</span><span class="sxs-lookup"><span data-stu-id="b3f95-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="b3f95-109">接口表示调试器帮助程序任务。</span><span class="sxs-lookup"><span data-stu-id="b3f95-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="b3f95-110">接口表示终结器任务。</span><span class="sxs-lookup"><span data-stu-id="b3f95-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="b3f95-111">接口表示垃圾回收作业。</span><span class="sxs-lookup"><span data-stu-id="b3f95-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="b3f95-112">接口表示入口线程任务。</span><span class="sxs-lookup"><span data-stu-id="b3f95-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="b3f95-113">接口表示一个 I/O 线程任务或完成端口线程任务。</span><span class="sxs-lookup"><span data-stu-id="b3f95-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="b3f95-114">接口表示计时器线程任务。</span><span class="sxs-lookup"><span data-stu-id="b3f95-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="b3f95-115">接口表示等待线程任务。</span><span class="sxs-lookup"><span data-stu-id="b3f95-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="b3f95-116">接口表示一个工作线程任务。</span><span class="sxs-lookup"><span data-stu-id="b3f95-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="b3f95-117">任务是未知的。</span><span class="sxs-lookup"><span data-stu-id="b3f95-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="b3f95-118">接口表示一个用户任务。</span><span class="sxs-lookup"><span data-stu-id="b3f95-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3f95-119">惠?</span><span class="sxs-lookup"><span data-stu-id="b3f95-119">Requirements</span></span>  
 <span data-ttu-id="b3f95-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b3f95-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3f95-121">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b3f95-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b3f95-122">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b3f95-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3f95-123">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3f95-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f95-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3f95-124">See Also</span></span>  
 [<span data-ttu-id="b3f95-125">承载枚举</span><span class="sxs-lookup"><span data-stu-id="b3f95-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
