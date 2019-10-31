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
ms.openlocfilehash: bc956827ad59fc655137e4147e6d98b6d097d470
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138193"
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="c45b7-102">ETaskType 枚举</span><span class="sxs-lookup"><span data-stu-id="c45b7-102">ETaskType Enumeration</span></span>
<span data-ttu-id="c45b7-103">包含一些值，这些值指示由[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)或[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)接口表示的任务的类型。</span><span class="sxs-lookup"><span data-stu-id="c45b7-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) or an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c45b7-104">语法</span><span class="sxs-lookup"><span data-stu-id="c45b7-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="c45b7-105">Members</span><span class="sxs-lookup"><span data-stu-id="c45b7-105">Members</span></span>  
  
|<span data-ttu-id="c45b7-106">成员</span><span class="sxs-lookup"><span data-stu-id="c45b7-106">Member</span></span>|<span data-ttu-id="c45b7-107">描述</span><span class="sxs-lookup"><span data-stu-id="c45b7-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="c45b7-108">接口表示应用程序域卸载任务。</span><span class="sxs-lookup"><span data-stu-id="c45b7-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="c45b7-109">接口表示调试器帮助器任务。</span><span class="sxs-lookup"><span data-stu-id="c45b7-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="c45b7-110">接口表示终结器任务。</span><span class="sxs-lookup"><span data-stu-id="c45b7-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="c45b7-111">接口表示垃圾回收任务。</span><span class="sxs-lookup"><span data-stu-id="c45b7-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="c45b7-112">接口表示一个 "入口线程" 任务。</span><span class="sxs-lookup"><span data-stu-id="c45b7-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="c45b7-113">接口表示 i/o 线程任务或完成端口线程任务。</span><span class="sxs-lookup"><span data-stu-id="c45b7-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="c45b7-114">接口表示计时器线程任务。</span><span class="sxs-lookup"><span data-stu-id="c45b7-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="c45b7-115">接口表示等待线程任务。</span><span class="sxs-lookup"><span data-stu-id="c45b7-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="c45b7-116">接口表示工作线程任务。</span><span class="sxs-lookup"><span data-stu-id="c45b7-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="c45b7-117">任务未知。</span><span class="sxs-lookup"><span data-stu-id="c45b7-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="c45b7-118">接口表示用户任务。</span><span class="sxs-lookup"><span data-stu-id="c45b7-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c45b7-119">要求</span><span class="sxs-lookup"><span data-stu-id="c45b7-119">Requirements</span></span>  
 <span data-ttu-id="c45b7-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c45b7-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c45b7-121">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c45b7-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c45b7-122">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c45b7-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c45b7-123">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c45b7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c45b7-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="c45b7-124">See also</span></span>

- [<span data-ttu-id="c45b7-125">承载枚举</span><span class="sxs-lookup"><span data-stu-id="c45b7-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
