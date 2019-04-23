---
title: ICLRPolicyManager 接口
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2eeccc4dfd7a7147fe791444eeeca2bd3a844305
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211036"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="c7bc0-102">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="c7bc0-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="c7bc0-103">提供了使宿主可以指定发生错误和超时时所采取的策略操作的方法。</span><span class="sxs-lookup"><span data-stu-id="c7bc0-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7bc0-104">方法</span><span class="sxs-lookup"><span data-stu-id="c7bc0-104">Methods</span></span>  
  
|<span data-ttu-id="c7bc0-105">方法</span><span class="sxs-lookup"><span data-stu-id="c7bc0-105">Method</span></span>|<span data-ttu-id="c7bc0-106">描述</span><span class="sxs-lookup"><span data-stu-id="c7bc0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c7bc0-107">SetActionOnFailure 方法</span><span class="sxs-lookup"><span data-stu-id="c7bc0-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="c7bc0-108">指定公共语言运行时 (CLR) 指定的故障发生时应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="c7bc0-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="c7bc0-109">SetActionOnTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="c7bc0-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="c7bc0-110">指定当指定的操作超时时，CLR 应采取的策略操作。</span><span class="sxs-lookup"><span data-stu-id="c7bc0-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="c7bc0-111">SetDefaultAction 方法</span><span class="sxs-lookup"><span data-stu-id="c7bc0-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="c7bc0-112">指定 CLR 在发生指定的操作时应采取的策略操作。</span><span class="sxs-lookup"><span data-stu-id="c7bc0-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="c7bc0-113">SetTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="c7bc0-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="c7bc0-114">设置指定的操作的超时值。</span><span class="sxs-lookup"><span data-stu-id="c7bc0-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="c7bc0-115">SetTimeoutAndAction 方法</span><span class="sxs-lookup"><span data-stu-id="c7bc0-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="c7bc0-116">设置指定的操作的超时值，并指定 CLR 发生该操作时应采取的策略操作。</span><span class="sxs-lookup"><span data-stu-id="c7bc0-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="c7bc0-117">SetUnhandledExceptionPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="c7bc0-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="c7bc0-118">发生未处理的异常时指定的 clr 的行为。</span><span class="sxs-lookup"><span data-stu-id="c7bc0-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c7bc0-119">要求</span><span class="sxs-lookup"><span data-stu-id="c7bc0-119">Requirements</span></span>  
 <span data-ttu-id="c7bc0-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c7bc0-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7bc0-121">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c7bc0-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7bc0-122">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c7bc0-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7bc0-123">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7bc0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7bc0-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7bc0-124">See also</span></span>

- [<span data-ttu-id="c7bc0-125">EClrFailure 枚举</span><span class="sxs-lookup"><span data-stu-id="c7bc0-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="c7bc0-126">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="c7bc0-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="c7bc0-127">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="c7bc0-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="c7bc0-128">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="c7bc0-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
