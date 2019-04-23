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
ms.openlocfilehash: 9d71b7e1265110a70329377ce8ab7430e1943c49
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124017"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="8702a-102">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="8702a-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="8702a-103">允许公共语言运行时 (CLR) 来维护由宿主实现的安全上下文信息。</span><span class="sxs-lookup"><span data-stu-id="8702a-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8702a-104">方法</span><span class="sxs-lookup"><span data-stu-id="8702a-104">Methods</span></span>  
  
|<span data-ttu-id="8702a-105">方法</span><span class="sxs-lookup"><span data-stu-id="8702a-105">Method</span></span>|<span data-ttu-id="8702a-106">描述</span><span class="sxs-lookup"><span data-stu-id="8702a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8702a-107">Capture 方法</span><span class="sxs-lookup"><span data-stu-id="8702a-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="8702a-108">获取的克隆`IHostSecurityContext`实例返回通过调用[ihostsecuritymanager:: Getsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)。</span><span class="sxs-lookup"><span data-stu-id="8702a-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8702a-109">备注</span><span class="sxs-lookup"><span data-stu-id="8702a-109">Remarks</span></span>  
 <span data-ttu-id="8702a-110">主机可以通过 CLR 和用户代码控制对线程令牌的所有代码访问权限。</span><span class="sxs-lookup"><span data-stu-id="8702a-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="8702a-111">它还可确保完整的安全跨异步操作或具有受限制的代码访问权限的代码点传递上下文信息。</span><span class="sxs-lookup"><span data-stu-id="8702a-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="8702a-112">`IHostSecurityContext` 封装此安全上下文信息，这是不透明的运行时。</span><span class="sxs-lookup"><span data-stu-id="8702a-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="8702a-113">在运行时捕获此信息使用`Capture`，并将其移动多个线程池工作项调度、 终结器执行和模块和类构造函数。</span><span class="sxs-lookup"><span data-stu-id="8702a-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8702a-114">要求</span><span class="sxs-lookup"><span data-stu-id="8702a-114">Requirements</span></span>  
 <span data-ttu-id="8702a-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8702a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8702a-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8702a-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8702a-117">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8702a-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8702a-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8702a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8702a-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="8702a-119">See also</span></span>

- [<span data-ttu-id="8702a-120">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="8702a-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="8702a-121">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="8702a-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="8702a-122">承载接口</span><span class="sxs-lookup"><span data-stu-id="8702a-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
