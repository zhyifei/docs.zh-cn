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
ms.openlocfilehash: 993d16818b25dfefe1f53c7afd06bc9857d9eb24
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121525"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="c4b82-102">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="c4b82-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="c4b82-103">允许公共语言运行时（CLR）维护宿主实现的安全上下文信息。</span><span class="sxs-lookup"><span data-stu-id="c4b82-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c4b82-104">方法</span><span class="sxs-lookup"><span data-stu-id="c4b82-104">Methods</span></span>  
  
|<span data-ttu-id="c4b82-105">方法</span><span class="sxs-lookup"><span data-stu-id="c4b82-105">Method</span></span>|<span data-ttu-id="c4b82-106">描述</span><span class="sxs-lookup"><span data-stu-id="c4b82-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c4b82-107">Capture 方法</span><span class="sxs-lookup"><span data-stu-id="c4b82-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="c4b82-108">获取从对[IHostSecurityManager：： GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)的调用返回的 `IHostSecurityContext` 实例的克隆。</span><span class="sxs-lookup"><span data-stu-id="c4b82-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4b82-109">备注</span><span class="sxs-lookup"><span data-stu-id="c4b82-109">Remarks</span></span>  
 <span data-ttu-id="c4b82-110">宿主可以通过 CLR 和用户代码控制对线程标记的所有代码访问。</span><span class="sxs-lookup"><span data-stu-id="c4b82-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="c4b82-111">它还可以确保在异步操作或代码点之间跨受限制的代码访问传递完整的安全上下文信息。</span><span class="sxs-lookup"><span data-stu-id="c4b82-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="c4b82-112">`IHostSecurityContext` 封装此安全上下文信息，这对于运行时是不透明的。</span><span class="sxs-lookup"><span data-stu-id="c4b82-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="c4b82-113">运行时使用 `Capture`捕获此信息，并将其移动到线程池辅助角色项调度、终结器执行和模块和类构造函数中。</span><span class="sxs-lookup"><span data-stu-id="c4b82-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4b82-114">要求</span><span class="sxs-lookup"><span data-stu-id="c4b82-114">Requirements</span></span>  
 <span data-ttu-id="c4b82-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b82-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4b82-116">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c4b82-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4b82-117">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c4b82-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4b82-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4b82-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b82-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4b82-119">See also</span></span>

- [<span data-ttu-id="c4b82-120">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="c4b82-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="c4b82-121">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="c4b82-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="c4b82-122">承载接口</span><span class="sxs-lookup"><span data-stu-id="c4b82-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
