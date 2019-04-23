---
title: ICorThreadpool::CorChangeTimer 方法
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorChangeTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorChangeTimer
helpviewer_keywords:
- CorChangeTimer method [.NET Framework hosting]
- ICorThreadpool::CorChangeTimer method [.NET Framework hosting]
ms.assetid: 82b03a59-5a87-43ed-9b75-e04b256e1a46
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de4a61f188bc6419b52f168c8bbbf43ad91fa19e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159596"
---
# <a name="icorthreadpoolcorchangetimer-method"></a><span data-ttu-id="49ffc-102">ICorThreadpool::CorChangeTimer 方法</span><span class="sxs-lookup"><span data-stu-id="49ffc-102">ICorThreadpool::CorChangeTimer Method</span></span>
<span data-ttu-id="49ffc-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="49ffc-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49ffc-104">语法</span><span class="sxs-lookup"><span data-stu-id="49ffc-104">Syntax</span></span>  
  
```  
HRESULT CorChangeTimer (  
    [in]  HANDLE Timer,   
    [in]  ULONG  DueTime,   
    [in]  ULONG  Period,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="49ffc-105">要求</span><span class="sxs-lookup"><span data-stu-id="49ffc-105">Requirements</span></span>  
 <span data-ttu-id="49ffc-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="49ffc-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49ffc-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="49ffc-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="49ffc-108">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="49ffc-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49ffc-109">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49ffc-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49ffc-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="49ffc-110">See also</span></span>

- [<span data-ttu-id="49ffc-111">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="49ffc-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
