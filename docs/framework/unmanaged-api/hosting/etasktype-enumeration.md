---
title: ETaskType 枚举
ms.date: 03/30/2017
api_name:
- ETaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ETaskType
helpviewer_keywords:
- ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f256195a4cd5b18f568e05156db867aa5dba9161
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61627958"
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="623af-102">ETaskType 枚举</span><span class="sxs-lookup"><span data-stu-id="623af-102">ETaskType Enumeration</span></span>
<span data-ttu-id="623af-103">包含指示表示通过以下任一方法的任务的类型值[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)或[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="623af-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) or an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="623af-104">语法</span><span class="sxs-lookup"><span data-stu-id="623af-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="623af-105">成员</span><span class="sxs-lookup"><span data-stu-id="623af-105">Members</span></span>  
  
|<span data-ttu-id="623af-106">成员</span><span class="sxs-lookup"><span data-stu-id="623af-106">Member</span></span>|<span data-ttu-id="623af-107">描述</span><span class="sxs-lookup"><span data-stu-id="623af-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="623af-108">该接口表示应用程序域正在卸载任务。</span><span class="sxs-lookup"><span data-stu-id="623af-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="623af-109">该接口表示调试器帮助程序任务。</span><span class="sxs-lookup"><span data-stu-id="623af-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="623af-110">该接口表示终结器任务。</span><span class="sxs-lookup"><span data-stu-id="623af-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="623af-111">该接口表示垃圾回收任务。</span><span class="sxs-lookup"><span data-stu-id="623af-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="623af-112">该接口表示入口线程任务。</span><span class="sxs-lookup"><span data-stu-id="623af-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="623af-113">该接口表示一个 I/O 线程任务或完成端口线程任务。</span><span class="sxs-lookup"><span data-stu-id="623af-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="623af-114">该接口表示计时器线程任务。</span><span class="sxs-lookup"><span data-stu-id="623af-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="623af-115">该接口表示等待线程任务。</span><span class="sxs-lookup"><span data-stu-id="623af-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="623af-116">该接口表示工作线程任务。</span><span class="sxs-lookup"><span data-stu-id="623af-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="623af-117">该任务是未知的。</span><span class="sxs-lookup"><span data-stu-id="623af-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="623af-118">该接口表示一个用户任务。</span><span class="sxs-lookup"><span data-stu-id="623af-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="623af-119">要求</span><span class="sxs-lookup"><span data-stu-id="623af-119">Requirements</span></span>  
 <span data-ttu-id="623af-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="623af-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="623af-121">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="623af-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="623af-122">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="623af-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="623af-123">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="623af-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="623af-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="623af-124">See also</span></span>

- [<span data-ttu-id="623af-125">承载枚举</span><span class="sxs-lookup"><span data-stu-id="623af-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
