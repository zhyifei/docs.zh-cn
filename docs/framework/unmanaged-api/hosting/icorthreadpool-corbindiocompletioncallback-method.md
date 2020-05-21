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
ms.openlocfilehash: c3ebe0bcd546feeeb0aa8c962f2b4c8b0562cb6f
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760441"
---
# <a name="icorthreadpoolcorbindiocompletioncallback-method"></a><span data-ttu-id="fffdf-102">ICorThreadpool::CorBindIoCompletionCallback 方法</span><span class="sxs-lookup"><span data-stu-id="fffdf-102">ICorThreadpool::CorBindIoCompletionCallback Method</span></span>
<span data-ttu-id="fffdf-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="fffdf-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fffdf-104">语法</span><span class="sxs-lookup"><span data-stu-id="fffdf-104">Syntax</span></span>  
  
```cpp  
HRESULT CorBindIoCompletionCallback (  
    [in] HANDLE                          fileHandle,  
    [in] LPOVERLAPPED_COMPLETION_ROUTINE callback  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="fffdf-105">要求</span><span class="sxs-lookup"><span data-stu-id="fffdf-105">Requirements</span></span>  
 <span data-ttu-id="fffdf-106">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fffdf-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fffdf-107">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fffdf-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fffdf-108">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="fffdf-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fffdf-109">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fffdf-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fffdf-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fffdf-110">See also</span></span>

- [<span data-ttu-id="fffdf-111">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="fffdf-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
