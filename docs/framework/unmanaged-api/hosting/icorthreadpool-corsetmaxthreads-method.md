---
title: ICorThreadpool::CorSetMaxThreads 方法
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorSetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetMaxThreads
helpviewer_keywords:
- ICorThreadpool::CorSetMaxThreads method [.NET Framework hosting]
- CorSetMaxThreads method [.NET Framework hosting]
ms.assetid: 4a846238-df4e-4060-ba3b-5173f6a51e85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48d84d5c45ea8e1af1da44480410692d46162810
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198239"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="2e6c1-102">ICorThreadpool::CorSetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="2e6c1-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="2e6c1-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="2e6c1-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e6c1-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e6c1-104">Syntax</span></span>  
  
```  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="2e6c1-105">要求</span><span class="sxs-lookup"><span data-stu-id="2e6c1-105">Requirements</span></span>  
 <span data-ttu-id="2e6c1-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2e6c1-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e6c1-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2e6c1-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e6c1-108">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2e6c1-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2e6c1-109">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="2e6c1-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2e6c1-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e6c1-110">See also</span></span>

- [<span data-ttu-id="2e6c1-111">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="2e6c1-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
