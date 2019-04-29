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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b24e278b3449d0e17377495cef0f445c1ebed734
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763264"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="eabfb-102">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="eabfb-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="eabfb-103">提供用于配置公共语言运行时 (CLR) 方法。</span><span class="sxs-lookup"><span data-stu-id="eabfb-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eabfb-104">方法</span><span class="sxs-lookup"><span data-stu-id="eabfb-104">Methods</span></span>  
  
|<span data-ttu-id="eabfb-105">方法</span><span class="sxs-lookup"><span data-stu-id="eabfb-105">Method</span></span>|<span data-ttu-id="eabfb-106">描述</span><span class="sxs-lookup"><span data-stu-id="eabfb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eabfb-107">AddDebuggerSpecialThread 方法</span><span class="sxs-lookup"><span data-stu-id="eabfb-107">AddDebuggerSpecialThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="eabfb-108">指示调试服务应允许在特定线程时调试器已在托管或非托管调试方案过程中停止的应用程序继续执行。</span><span class="sxs-lookup"><span data-stu-id="eabfb-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="eabfb-109">SetDebuggerThreadControl 方法</span><span class="sxs-lookup"><span data-stu-id="eabfb-109">SetDebuggerThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="eabfb-110">设置调试服务将调用 CLR 线程阻止和解除阻止以进行调试的回调接口。</span><span class="sxs-lookup"><span data-stu-id="eabfb-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="eabfb-111">SetGCHostControl 方法</span><span class="sxs-lookup"><span data-stu-id="eabfb-111">SetGCHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="eabfb-112">设置要由垃圾回收器用于请求的主机，若要更改的虚拟内存限制的回调接口。</span><span class="sxs-lookup"><span data-stu-id="eabfb-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="eabfb-113">SetGCThreadControl 方法</span><span class="sxs-lookup"><span data-stu-id="eabfb-113">SetGCThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="eabfb-114">设置回调接口来调度线程，以防止因阻塞而垃圾回收的非运行时任务。</span><span class="sxs-lookup"><span data-stu-id="eabfb-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eabfb-115">要求</span><span class="sxs-lookup"><span data-stu-id="eabfb-115">Requirements</span></span>  
 <span data-ttu-id="eabfb-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eabfb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eabfb-117">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eabfb-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eabfb-118">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="eabfb-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eabfb-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eabfb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eabfb-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="eabfb-120">See also</span></span>

- [<span data-ttu-id="eabfb-121">承载接口</span><span class="sxs-lookup"><span data-stu-id="eabfb-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="eabfb-122">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="eabfb-122">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
