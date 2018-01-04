---
title: "IApartmentCallback::DoCallback 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IApartmentCallback.DoCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 06aaab6d4ad7d33bbdc52a38c999cc925eee1666
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="58d91-102">IApartmentCallback::DoCallback 方法</span><span class="sxs-lookup"><span data-stu-id="58d91-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="58d91-103">执行的单元内的指定的函数。</span><span class="sxs-lookup"><span data-stu-id="58d91-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58d91-104">语法</span><span class="sxs-lookup"><span data-stu-id="58d91-104">Syntax</span></span>  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58d91-105">参数</span><span class="sxs-lookup"><span data-stu-id="58d91-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="58d91-106">[in]指向要在单元内执行的函数的指针。</span><span class="sxs-lookup"><span data-stu-id="58d91-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="58d91-107">[in]指向函数的自变量的指针。</span><span class="sxs-lookup"><span data-stu-id="58d91-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58d91-108">惠?</span><span class="sxs-lookup"><span data-stu-id="58d91-108">Requirements</span></span>  
 <span data-ttu-id="58d91-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58d91-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58d91-110">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="58d91-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58d91-111">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="58d91-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58d91-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58d91-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58d91-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="58d91-113">See Also</span></span>  
 [<span data-ttu-id="58d91-114">IApartmentCallback 接口</span><span class="sxs-lookup"><span data-stu-id="58d91-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
