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
ms.openlocfilehash: b7cbc14c1b84ae5605f7aaed688acbedbb51d056
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437126"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="329c8-102">ICorThreadpool::CorSetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="329c8-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="329c8-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="329c8-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="329c8-104">语法</span><span class="sxs-lookup"><span data-stu-id="329c8-104">Syntax</span></span>  
  
```  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="329c8-105">要求</span><span class="sxs-lookup"><span data-stu-id="329c8-105">Requirements</span></span>  
 <span data-ttu-id="329c8-106">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="329c8-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="329c8-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="329c8-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="329c8-108">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="329c8-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="329c8-109">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="329c8-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="329c8-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="329c8-110">See Also</span></span>  
 [<span data-ttu-id="329c8-111">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="329c8-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
