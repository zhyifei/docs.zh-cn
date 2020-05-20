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
ms.openlocfilehash: 631301a10aee96bb00aeda6b0b8695f0aea186a8
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703476"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="07d38-102">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="07d38-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="07d38-103">提供允许主机指定在发生故障和超时时要执行的策略操作的方法。</span><span class="sxs-lookup"><span data-stu-id="07d38-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07d38-104">方法</span><span class="sxs-lookup"><span data-stu-id="07d38-104">Methods</span></span>  
  
|<span data-ttu-id="07d38-105">方法</span><span class="sxs-lookup"><span data-stu-id="07d38-105">Method</span></span>|<span data-ttu-id="07d38-106">说明</span><span class="sxs-lookup"><span data-stu-id="07d38-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="07d38-107">SetActionOnFailure 方法</span><span class="sxs-lookup"><span data-stu-id="07d38-107">SetActionOnFailure Method</span></span>](iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="07d38-108">指定发生指定的故障时公共语言运行时（CLR）应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="07d38-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="07d38-109">SetActionOnTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="07d38-109">SetActionOnTimeout Method</span></span>](iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="07d38-110">指定在指定操作超时时 CLR 应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="07d38-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="07d38-111">SetDefaultAction 方法</span><span class="sxs-lookup"><span data-stu-id="07d38-111">SetDefaultAction Method</span></span>](iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="07d38-112">指定发生指定操作时 CLR 应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="07d38-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="07d38-113">SetTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="07d38-113">SetTimeout Method</span></span>](iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="07d38-114">设置指定操作的超时值。</span><span class="sxs-lookup"><span data-stu-id="07d38-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="07d38-115">SetTimeoutAndAction 方法</span><span class="sxs-lookup"><span data-stu-id="07d38-115">SetTimeoutAndAction Method</span></span>](iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="07d38-116">设置指定操作的超时值，并指定该操作发生时 CLR 应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="07d38-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="07d38-117">SetUnhandledExceptionPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="07d38-117">SetUnhandledExceptionPolicy Method</span></span>](iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="07d38-118">指定发生未经处理的异常时 CLR 的行为。</span><span class="sxs-lookup"><span data-stu-id="07d38-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="07d38-119">要求</span><span class="sxs-lookup"><span data-stu-id="07d38-119">Requirements</span></span>  
 <span data-ttu-id="07d38-120">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="07d38-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07d38-121">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="07d38-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="07d38-122">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="07d38-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07d38-123">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07d38-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07d38-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07d38-124">See also</span></span>

- [<span data-ttu-id="07d38-125">EClrFailure 枚举</span><span class="sxs-lookup"><span data-stu-id="07d38-125">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="07d38-126">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="07d38-126">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="07d38-127">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="07d38-127">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="07d38-128">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="07d38-128">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
