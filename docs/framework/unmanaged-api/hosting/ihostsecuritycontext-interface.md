---
title: IHostSecurityContext 接口
ms.date: 03/30/2017
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c2500f013584ef4722ceaaaee91d5db54991639
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439294"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="a8051-102">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="a8051-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="a8051-103">允许公共语言运行时 (CLR) 来维护由宿主实现的安全上下文信息。</span><span class="sxs-lookup"><span data-stu-id="a8051-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8051-104">方法</span><span class="sxs-lookup"><span data-stu-id="a8051-104">Methods</span></span>  
  
|<span data-ttu-id="a8051-105">方法</span><span class="sxs-lookup"><span data-stu-id="a8051-105">Method</span></span>|<span data-ttu-id="a8051-106">描述</span><span class="sxs-lookup"><span data-stu-id="a8051-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8051-107">Capture 方法</span><span class="sxs-lookup"><span data-stu-id="a8051-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="a8051-108">获取的复本`IHostSecurityContext`实例返回到调用[ihostsecuritymanager:: Getsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)。</span><span class="sxs-lookup"><span data-stu-id="a8051-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8051-109">备注</span><span class="sxs-lookup"><span data-stu-id="a8051-109">Remarks</span></span>  
 <span data-ttu-id="a8051-110">主机可以控制的 CLR 和用户代码对线程标记的所有代码访问。</span><span class="sxs-lookup"><span data-stu-id="a8051-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="a8051-111">它还可确保完整的安全性在异步操作或具有受限制的代码访问权限的代码点间传递上下文信息。</span><span class="sxs-lookup"><span data-stu-id="a8051-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="a8051-112">`IHostSecurityContext` 封装此安全上下文信息，这就是不透明的运行时。</span><span class="sxs-lookup"><span data-stu-id="a8051-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="a8051-113">运行时捕获此信息使用`Capture`，并将其移动在线程池工作项调度、 终结器执行和模块和类构造函数。</span><span class="sxs-lookup"><span data-stu-id="a8051-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8051-114">要求</span><span class="sxs-lookup"><span data-stu-id="a8051-114">Requirements</span></span>  
 <span data-ttu-id="a8051-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a8051-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8051-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a8051-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a8051-117">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a8051-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8051-118">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8051-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8051-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8051-119">See Also</span></span>  
 [<span data-ttu-id="a8051-120">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="a8051-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="a8051-121">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="a8051-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="a8051-122">承载接口</span><span class="sxs-lookup"><span data-stu-id="a8051-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
