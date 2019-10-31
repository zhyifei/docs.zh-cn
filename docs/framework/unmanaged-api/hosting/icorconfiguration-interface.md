---
title: ICorConfiguration 接口
ms.date: 03/30/2017
api_name:
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
ms.openlocfilehash: 80bb68486e555d6c96cf8ee56ed6d60e41c7c5c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127807"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="ff830-102">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="ff830-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="ff830-103">提供用于配置公共语言运行时（CLR）的方法。</span><span class="sxs-lookup"><span data-stu-id="ff830-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff830-104">方法</span><span class="sxs-lookup"><span data-stu-id="ff830-104">Methods</span></span>  
  
|<span data-ttu-id="ff830-105">方法</span><span class="sxs-lookup"><span data-stu-id="ff830-105">Method</span></span>|<span data-ttu-id="ff830-106">描述</span><span class="sxs-lookup"><span data-stu-id="ff830-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff830-107">AddDebuggerSpecialThread 方法</span><span class="sxs-lookup"><span data-stu-id="ff830-107">AddDebuggerSpecialThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="ff830-108">向调试服务指示当调试器在托管或非托管调试方案中停止应用程序时，应允许特定线程继续执行。</span><span class="sxs-lookup"><span data-stu-id="ff830-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="ff830-109">SetDebuggerThreadControl 方法</span><span class="sxs-lookup"><span data-stu-id="ff830-109">SetDebuggerThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="ff830-110">设置在阻止和取消阻止 CLR 线程以进行调试时，调试服务将调用的回调接口。</span><span class="sxs-lookup"><span data-stu-id="ff830-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="ff830-111">SetGCHostControl 方法</span><span class="sxs-lookup"><span data-stu-id="ff830-111">SetGCHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="ff830-112">设置垃圾回收器用于请求主机更改虚拟内存限制的回调接口。</span><span class="sxs-lookup"><span data-stu-id="ff830-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="ff830-113">SetGCThreadControl 方法</span><span class="sxs-lookup"><span data-stu-id="ff830-113">SetGCThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="ff830-114">设置回调接口，用于为非运行时任务计划线程，否则将阻止垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="ff830-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ff830-115">要求</span><span class="sxs-lookup"><span data-stu-id="ff830-115">Requirements</span></span>  
 <span data-ttu-id="ff830-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ff830-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff830-117">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ff830-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff830-118">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="ff830-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff830-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff830-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff830-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff830-120">See also</span></span>

- [<span data-ttu-id="ff830-121">承载接口</span><span class="sxs-lookup"><span data-stu-id="ff830-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ff830-122">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="ff830-122">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
