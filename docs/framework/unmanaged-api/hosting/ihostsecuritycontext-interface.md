---
title: "IHostSecurityContext 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityContext
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityContext
helpviewer_keywords: IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1d3c616ced761b696f50e9207e6fad312f06c31c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="25f0b-102">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="25f0b-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="25f0b-103">允许公共语言运行时 (CLR) 来维护由宿主实现的安全上下文信息。</span><span class="sxs-lookup"><span data-stu-id="25f0b-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="25f0b-104">方法</span><span class="sxs-lookup"><span data-stu-id="25f0b-104">Methods</span></span>  
  
|<span data-ttu-id="25f0b-105">方法</span><span class="sxs-lookup"><span data-stu-id="25f0b-105">Method</span></span>|<span data-ttu-id="25f0b-106">描述</span><span class="sxs-lookup"><span data-stu-id="25f0b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="25f0b-107">Capture 方法</span><span class="sxs-lookup"><span data-stu-id="25f0b-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="25f0b-108">获取的复本`IHostSecurityContext`实例返回到调用[ihostsecuritymanager:: Getsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)。</span><span class="sxs-lookup"><span data-stu-id="25f0b-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25f0b-109">备注</span><span class="sxs-lookup"><span data-stu-id="25f0b-109">Remarks</span></span>  
 <span data-ttu-id="25f0b-110">主机可以控制的 CLR 和用户代码对线程标记的所有代码访问。</span><span class="sxs-lookup"><span data-stu-id="25f0b-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="25f0b-111">它还可确保完整的安全性在异步操作或具有受限制的代码访问权限的代码点间传递上下文信息。</span><span class="sxs-lookup"><span data-stu-id="25f0b-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="25f0b-112">`IHostSecurityContext`封装此安全上下文信息，这就是不透明的运行时。</span><span class="sxs-lookup"><span data-stu-id="25f0b-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="25f0b-113">运行时捕获此信息使用`Capture`，并将其移动在线程池工作项调度、 终结器执行和模块和类构造函数。</span><span class="sxs-lookup"><span data-stu-id="25f0b-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25f0b-114">要求</span><span class="sxs-lookup"><span data-stu-id="25f0b-114">Requirements</span></span>  
 <span data-ttu-id="25f0b-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="25f0b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25f0b-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="25f0b-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="25f0b-117">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="25f0b-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="25f0b-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25f0b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25f0b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25f0b-119">See Also</span></span>  
 [<span data-ttu-id="25f0b-120">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="25f0b-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="25f0b-121">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="25f0b-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="25f0b-122">承载接口</span><span class="sxs-lookup"><span data-stu-id="25f0b-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
