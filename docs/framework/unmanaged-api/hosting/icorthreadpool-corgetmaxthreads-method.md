---
title: ICorThreadpool::CorGetMaxThreads 方法
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorGetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetMaxThreads
helpviewer_keywords:
- CorGetMaxThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetMaxThreads method [.NET Framework hosting]
ms.assetid: 2861533a-cda0-47b3-b716-0d363505289b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 33cbbf5d9be682b82b7e21034b1db206f0ba4ec5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646184"
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="b04dc-102">ICorThreadpool::CorGetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="b04dc-102">ICorThreadpool::CorGetMaxThreads Method</span></span>
<span data-ttu-id="b04dc-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="b04dc-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b04dc-104">语法</span><span class="sxs-lookup"><span data-stu-id="b04dc-104">Syntax</span></span>  
  
```  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="b04dc-105">要求</span><span class="sxs-lookup"><span data-stu-id="b04dc-105">Requirements</span></span>  
 <span data-ttu-id="b04dc-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b04dc-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b04dc-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b04dc-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b04dc-108">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b04dc-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b04dc-109">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b04dc-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b04dc-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="b04dc-110">See also</span></span>
- [<span data-ttu-id="b04dc-111">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="b04dc-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
