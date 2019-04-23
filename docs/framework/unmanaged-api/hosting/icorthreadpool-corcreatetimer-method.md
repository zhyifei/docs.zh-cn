---
title: ICorThreadpool::CorCreateTimer 方法
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorCreateTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCreateTimer
helpviewer_keywords:
- CorCreateTimer method [.NET Framework hosting]
- ICorThreadpool::CorCreateTimer method [.NET Framework hosting]
ms.assetid: 0d56ef25-30f1-4499-8a1f-76e7654ec614
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 69090618501abe7530ac7a04ae89a6bd3582e029
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111158"
---
# <a name="icorthreadpoolcorcreatetimer-method"></a><span data-ttu-id="bd9ef-102">ICorThreadpool::CorCreateTimer 方法</span><span class="sxs-lookup"><span data-stu-id="bd9ef-102">ICorThreadpool::CorCreateTimer Method</span></span>
<span data-ttu-id="bd9ef-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="bd9ef-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd9ef-104">语法</span><span class="sxs-lookup"><span data-stu-id="bd9ef-104">Syntax</span></span>  
  
```  
HRESULT CorCreateTimer (  
    [in]  HANDLE*             phNewTimer,  
    [in]  WAITORTIMERCALLBACK Callback,  
    [in]  PVOID               Parameter,  
    [in]  DWORD               DueTime,  
    [in]  DWORD               Period,  
    [out] BOOL*               result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="bd9ef-105">要求</span><span class="sxs-lookup"><span data-stu-id="bd9ef-105">Requirements</span></span>  
 <span data-ttu-id="bd9ef-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bd9ef-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd9ef-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bd9ef-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd9ef-108">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bd9ef-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd9ef-109">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd9ef-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd9ef-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd9ef-110">See also</span></span>

- [<span data-ttu-id="bd9ef-111">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="bd9ef-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
