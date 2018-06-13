---
title: ICorThreadpool::CorBindIoCompletionCallback 方法
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorBindIoCompletionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorBindIoCompletionCallback
helpviewer_keywords:
- CorBindIoCompletionCallback method [.NET Framework hosting]
- ICorThreadpool::CorBindIoCompletionCallback method [.NET Framework hosting]
ms.assetid: 2b159225-f09c-42f1-aa7c-44087e121249
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca1e594250c5447e6a2313843095010739a0cadb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436645"
---
# <a name="icorthreadpoolcorbindiocompletioncallback-method"></a><span data-ttu-id="8740f-102">ICorThreadpool::CorBindIoCompletionCallback 方法</span><span class="sxs-lookup"><span data-stu-id="8740f-102">ICorThreadpool::CorBindIoCompletionCallback Method</span></span>
<span data-ttu-id="8740f-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="8740f-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8740f-104">语法</span><span class="sxs-lookup"><span data-stu-id="8740f-104">Syntax</span></span>  
  
```  
HRESULT CorBindIoCompletionCallback (  
    [in] HANDLE                          fileHandle,  
    [in] LPOVERLAPPED_COMPLETION_ROUTINE callback  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="8740f-105">要求</span><span class="sxs-lookup"><span data-stu-id="8740f-105">Requirements</span></span>  
 <span data-ttu-id="8740f-106">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8740f-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8740f-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8740f-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8740f-108">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8740f-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8740f-109">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8740f-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8740f-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="8740f-110">See Also</span></span>  
 [<span data-ttu-id="8740f-111">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="8740f-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
