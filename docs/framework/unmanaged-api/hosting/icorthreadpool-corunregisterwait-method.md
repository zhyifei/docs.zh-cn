---
title: ICorThreadpool::CorUnregisterWait 方法
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorUnregisterWait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnregisterWait
helpviewer_keywords:
- CorUnregisterWait method [.NET Framework hosting]
- ICorThreadpool::CorUnregisterWait method [.NET Framework hosting]
ms.assetid: 42c933f1-30a8-4011-bdea-e117f3c3265e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eacc9152200b9b57e8a1c5506ecac2e0010fbe9f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698968"
---
# <a name="icorthreadpoolcorunregisterwait-method"></a><span data-ttu-id="f83bf-102">ICorThreadpool::CorUnregisterWait 方法</span><span class="sxs-lookup"><span data-stu-id="f83bf-102">ICorThreadpool::CorUnregisterWait Method</span></span>
<span data-ttu-id="f83bf-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="f83bf-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f83bf-104">语法</span><span class="sxs-lookup"><span data-stu-id="f83bf-104">Syntax</span></span>  
  
```  
HRESULT CorUnregisterWait (  
    [in] HANDLE hWaitObject,  
    [in] HANDLE CompletionEvent,  
    [out] BOOL* result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="f83bf-105">要求</span><span class="sxs-lookup"><span data-stu-id="f83bf-105">Requirements</span></span>  
 <span data-ttu-id="f83bf-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f83bf-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f83bf-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f83bf-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f83bf-108">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f83bf-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f83bf-109">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f83bf-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f83bf-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="f83bf-110">See also</span></span>
- [<span data-ttu-id="f83bf-111">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="f83bf-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
