---
title: IHostTaskManager::GetStackGuarantee 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetStackGuarantee
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetStackGuarantee
helpviewer_keywords:
- GetStackGuarantee method [.NET Framework hosting]
- IHostTaskManager::GetStackGuarantee method [.NET Framework hosting]
ms.assetid: 8176d732-c25c-4520-811d-e3310f339947
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 100bb73356379d2f251513bbbed0cf1e90752ff5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494367"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="2d216-102">IHostTaskManager::GetStackGuarantee 方法</span><span class="sxs-lookup"><span data-stu-id="2d216-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="2d216-103">获取的堆栈空间后的堆栈操作完成后，可保证，但在关闭进程之前的量。</span><span class="sxs-lookup"><span data-stu-id="2d216-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d216-104">语法</span><span class="sxs-lookup"><span data-stu-id="2d216-104">Syntax</span></span>  
  
```  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d216-105">参数</span><span class="sxs-lookup"><span data-stu-id="2d216-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="2d216-106">[out]指向可用的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="2d216-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d216-107">要求</span><span class="sxs-lookup"><span data-stu-id="2d216-107">Requirements</span></span>  
 <span data-ttu-id="2d216-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2d216-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d216-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2d216-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d216-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2d216-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d216-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d216-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d216-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d216-112">See also</span></span>
- [<span data-ttu-id="2d216-113">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="2d216-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
