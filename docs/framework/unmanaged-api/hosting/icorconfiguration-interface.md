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
ms.openlocfilehash: 63699f0af69b3a7623c5e9da156c2ff8ae83ccfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437503"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="45498-102">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="45498-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="45498-103">提供用于配置公共语言运行时 (CLR) 方法。</span><span class="sxs-lookup"><span data-stu-id="45498-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="45498-104">方法</span><span class="sxs-lookup"><span data-stu-id="45498-104">Methods</span></span>  
  
|<span data-ttu-id="45498-105">方法</span><span class="sxs-lookup"><span data-stu-id="45498-105">Method</span></span>|<span data-ttu-id="45498-106">描述</span><span class="sxs-lookup"><span data-stu-id="45498-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="45498-107">AddDebuggerSpecialThread 方法</span><span class="sxs-lookup"><span data-stu-id="45498-107">AddDebuggerSpecialThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="45498-108">指示应允许特定线程继续执行而调试器具有应用程序在托管或非托管调试方案期间停止调试服务。</span><span class="sxs-lookup"><span data-stu-id="45498-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="45498-109">SetDebuggerThreadControl 方法</span><span class="sxs-lookup"><span data-stu-id="45498-109">SetDebuggerThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="45498-110">设置调试服务将调用 CLR 线程阻止和解除阻止以用于调试的回调接口。</span><span class="sxs-lookup"><span data-stu-id="45498-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="45498-111">SetGCHostControl 方法</span><span class="sxs-lookup"><span data-stu-id="45498-111">SetGCHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="45498-112">设置要用于通过垃圾回收器请求主机后，若要更改的虚拟内存限制的回调接口。</span><span class="sxs-lookup"><span data-stu-id="45498-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="45498-113">SetGCThreadControl 方法</span><span class="sxs-lookup"><span data-stu-id="45498-113">SetGCThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="45498-114">设置计划对于非运行时任务，否则会阻止垃圾回收的线程使用的回调的接口。</span><span class="sxs-lookup"><span data-stu-id="45498-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="45498-115">要求</span><span class="sxs-lookup"><span data-stu-id="45498-115">Requirements</span></span>  
 <span data-ttu-id="45498-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="45498-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45498-117">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="45498-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="45498-118">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="45498-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="45498-119">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45498-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45498-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="45498-120">See Also</span></span>  
 [<span data-ttu-id="45498-121">承载接口</span><span class="sxs-lookup"><span data-stu-id="45498-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="45498-122">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="45498-122">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
