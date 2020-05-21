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
ms.openlocfilehash: 46ffdb21c1f3b501cc28afffc224349887af5644
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762742"
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="713de-102">ICorThreadpool::CorGetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="713de-102">ICorThreadpool::CorGetMaxThreads Method</span></span>
<span data-ttu-id="713de-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="713de-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="713de-104">语法</span><span class="sxs-lookup"><span data-stu-id="713de-104">Syntax</span></span>  
  
```cpp  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="713de-105">要求</span><span class="sxs-lookup"><span data-stu-id="713de-105">Requirements</span></span>  
 <span data-ttu-id="713de-106">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="713de-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="713de-107">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="713de-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="713de-108">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="713de-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="713de-109">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="713de-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="713de-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="713de-110">See also</span></span>

- [<span data-ttu-id="713de-111">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="713de-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
