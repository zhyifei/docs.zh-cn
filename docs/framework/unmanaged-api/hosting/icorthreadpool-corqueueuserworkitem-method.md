---
title: ICorThreadpool::CorQueueUserWorkItem 方法
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorQueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorQueueUserWorkItem method [.NET Framework hosting]
- CorQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 29ac7898-a7c7-433e-8f79-cd5237e0bab8
topic_type:
- apiref
ms.openlocfilehash: e4a62cc35de18f91324bfd428c24bb329fc9783b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133252"
---
# <a name="icorthreadpoolcorqueueuserworkitem-method"></a><span data-ttu-id="e233a-102">ICorThreadpool::CorQueueUserWorkItem 方法</span><span class="sxs-lookup"><span data-stu-id="e233a-102">ICorThreadpool::CorQueueUserWorkItem Method</span></span>
<span data-ttu-id="e233a-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="e233a-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e233a-104">语法</span><span class="sxs-lookup"><span data-stu-id="e233a-104">Syntax</span></span>  
  
```cpp  
HRESULT CorQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [in] BOOL                   executeOnlyOnce,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e233a-105">要求</span><span class="sxs-lookup"><span data-stu-id="e233a-105">Requirements</span></span>  
 <span data-ttu-id="e233a-106">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e233a-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e233a-107">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e233a-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e233a-108">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="e233a-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e233a-109">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e233a-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e233a-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="e233a-110">See also</span></span>

- [<span data-ttu-id="e233a-111">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="e233a-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
