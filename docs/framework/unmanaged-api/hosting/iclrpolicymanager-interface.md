---
title: "ICLRPolicyManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager
helpviewer_keywords: ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ce37f9beb0901eaf1bc98f5af3f8f99a7fedf1c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="7c615-102">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="7c615-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="7c615-103">提供使该主机可指定要执行发生故障和超时策略操作的方法。</span><span class="sxs-lookup"><span data-stu-id="7c615-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c615-104">方法</span><span class="sxs-lookup"><span data-stu-id="7c615-104">Methods</span></span>  
  
|<span data-ttu-id="7c615-105">方法</span><span class="sxs-lookup"><span data-stu-id="7c615-105">Method</span></span>|<span data-ttu-id="7c615-106">描述</span><span class="sxs-lookup"><span data-stu-id="7c615-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c615-107">SetActionOnFailure 方法</span><span class="sxs-lookup"><span data-stu-id="7c615-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="7c615-108">指定公共语言运行时 (CLR) 在发生指定的故障时应采取的策略操作。</span><span class="sxs-lookup"><span data-stu-id="7c615-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="7c615-109">SetActionOnTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="7c615-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="7c615-110">指定当指定的操作超时时，CLR 应采取的策略操作。</span><span class="sxs-lookup"><span data-stu-id="7c615-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="7c615-111">SetDefaultAction 方法</span><span class="sxs-lookup"><span data-stu-id="7c615-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="7c615-112">指定在指定的操作发生时，应执行 CLR 策略操作。</span><span class="sxs-lookup"><span data-stu-id="7c615-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="7c615-113">SetTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="7c615-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="7c615-114">设置指定的操作的超时值。</span><span class="sxs-lookup"><span data-stu-id="7c615-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="7c615-115">SetTimeoutAndAction 方法</span><span class="sxs-lookup"><span data-stu-id="7c615-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="7c615-116">设置一个超时值对于指定的操作，并指定 CLR 应采取的操作发生时的策略操作。</span><span class="sxs-lookup"><span data-stu-id="7c615-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="7c615-117">SetUnhandledExceptionPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="7c615-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="7c615-118">发生未处理的异常时，请指定的 CLR 的行为。</span><span class="sxs-lookup"><span data-stu-id="7c615-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c615-119">惠?</span><span class="sxs-lookup"><span data-stu-id="7c615-119">Requirements</span></span>  
 <span data-ttu-id="7c615-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c615-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c615-121">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7c615-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c615-122">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7c615-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c615-123">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c615-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c615-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c615-124">See Also</span></span>  
 [<span data-ttu-id="7c615-125">EClrFailure 枚举</span><span class="sxs-lookup"><span data-stu-id="7c615-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="7c615-126">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="7c615-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="7c615-127">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="7c615-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="7c615-128">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="7c615-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
