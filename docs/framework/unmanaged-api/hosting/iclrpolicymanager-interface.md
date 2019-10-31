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
ms.openlocfilehash: 59aa904d4c67326b60381d3476eaab179d7fa42b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140805"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="bc348-102">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="bc348-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="bc348-103">提供允许主机指定在发生故障和超时时要执行的策略操作的方法。</span><span class="sxs-lookup"><span data-stu-id="bc348-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bc348-104">方法</span><span class="sxs-lookup"><span data-stu-id="bc348-104">Methods</span></span>  
  
|<span data-ttu-id="bc348-105">方法</span><span class="sxs-lookup"><span data-stu-id="bc348-105">Method</span></span>|<span data-ttu-id="bc348-106">描述</span><span class="sxs-lookup"><span data-stu-id="bc348-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc348-107">SetActionOnFailure 方法</span><span class="sxs-lookup"><span data-stu-id="bc348-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="bc348-108">指定发生指定的故障时公共语言运行时（CLR）应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="bc348-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="bc348-109">SetActionOnTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="bc348-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="bc348-110">指定在指定操作超时时 CLR 应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="bc348-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="bc348-111">SetDefaultAction 方法</span><span class="sxs-lookup"><span data-stu-id="bc348-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="bc348-112">指定发生指定操作时 CLR 应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="bc348-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="bc348-113">SetTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="bc348-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="bc348-114">设置指定操作的超时值。</span><span class="sxs-lookup"><span data-stu-id="bc348-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="bc348-115">SetTimeoutAndAction 方法</span><span class="sxs-lookup"><span data-stu-id="bc348-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="bc348-116">设置指定操作的超时值，并指定该操作发生时 CLR 应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="bc348-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="bc348-117">SetUnhandledExceptionPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="bc348-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="bc348-118">指定发生未经处理的异常时 CLR 的行为。</span><span class="sxs-lookup"><span data-stu-id="bc348-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bc348-119">要求</span><span class="sxs-lookup"><span data-stu-id="bc348-119">Requirements</span></span>  
 <span data-ttu-id="bc348-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bc348-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc348-121">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bc348-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bc348-122">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="bc348-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc348-123">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc348-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc348-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc348-124">See also</span></span>

- [<span data-ttu-id="bc348-125">EClrFailure 枚举</span><span class="sxs-lookup"><span data-stu-id="bc348-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="bc348-126">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="bc348-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="bc348-127">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="bc348-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="bc348-128">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="bc348-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
