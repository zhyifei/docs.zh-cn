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
ms.openlocfilehash: 2963e2a31fd62470e3ed6933edb38119d286071b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59071969"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="b12ac-102">ICLRTaskManager::GetCurrentTaskType 方法</span><span class="sxs-lookup"><span data-stu-id="b12ac-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="b12ac-103">获取当前正在执行的任务的类型。</span><span class="sxs-lookup"><span data-stu-id="b12ac-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b12ac-104">语法</span><span class="sxs-lookup"><span data-stu-id="b12ac-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b12ac-105">参数</span><span class="sxs-lookup"><span data-stu-id="b12ac-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="b12ac-106">[out]指向的值的指针[ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md)枚举，指示当前正在执行的任务的类型。</span><span class="sxs-lookup"><span data-stu-id="b12ac-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b12ac-107">要求</span><span class="sxs-lookup"><span data-stu-id="b12ac-107">Requirements</span></span>  
 <span data-ttu-id="b12ac-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b12ac-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b12ac-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b12ac-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b12ac-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b12ac-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b12ac-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="b12ac-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b12ac-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="b12ac-112">See also</span></span>

- [<span data-ttu-id="b12ac-113">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="b12ac-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
