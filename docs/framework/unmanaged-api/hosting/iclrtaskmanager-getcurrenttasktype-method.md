---
title: ICLRTaskManager::GetCurrentTaskType 方法
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTaskType
helpviewer_keywords:
- GetCurrentTaskType method [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTaskType method [.NET Framework hosting]
ms.assetid: 6b0d9259-dbe2-45bb-b34d-990f60c73424
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f75538ff7f6c3266f44495b4170007a4802fee1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487442"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="7e554-102">ICLRTaskManager::GetCurrentTaskType 方法</span><span class="sxs-lookup"><span data-stu-id="7e554-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="7e554-103">获取当前正在执行的任务的类型。</span><span class="sxs-lookup"><span data-stu-id="7e554-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e554-104">语法</span><span class="sxs-lookup"><span data-stu-id="7e554-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e554-105">参数</span><span class="sxs-lookup"><span data-stu-id="7e554-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="7e554-106">[out]指向的值的指针[ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md)枚举，指示当前正在执行的任务的类型。</span><span class="sxs-lookup"><span data-stu-id="7e554-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e554-107">要求</span><span class="sxs-lookup"><span data-stu-id="7e554-107">Requirements</span></span>  
 <span data-ttu-id="7e554-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7e554-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e554-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7e554-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e554-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7e554-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e554-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e554-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e554-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e554-112">See also</span></span>
- [<span data-ttu-id="7e554-113">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="7e554-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
