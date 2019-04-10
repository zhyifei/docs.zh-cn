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
ms.openlocfilehash: bbf5c02972a8331b3dd5e35ffcc4213e094e532d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175729"
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="1b6be-102">ICorThreadpool::CorGetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="1b6be-102">ICorThreadpool::CorGetMaxThreads Method</span></span>
<span data-ttu-id="1b6be-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="1b6be-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b6be-104">语法</span><span class="sxs-lookup"><span data-stu-id="1b6be-104">Syntax</span></span>  
  
```  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="1b6be-105">要求</span><span class="sxs-lookup"><span data-stu-id="1b6be-105">Requirements</span></span>  
 <span data-ttu-id="1b6be-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1b6be-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b6be-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1b6be-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b6be-108">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1b6be-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="1b6be-109">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="1b6be-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1b6be-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b6be-110">See also</span></span>

- [<span data-ttu-id="1b6be-111">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="1b6be-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
