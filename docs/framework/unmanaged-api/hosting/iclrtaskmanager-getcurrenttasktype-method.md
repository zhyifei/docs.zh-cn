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
ms.openlocfilehash: 848255d44ce8637182f18288d30151a3f0df0912
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092165"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="23900-102">ICLRTaskManager::GetCurrentTaskType 方法</span><span class="sxs-lookup"><span data-stu-id="23900-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="23900-103">获取当前正在执行的任务的类型。</span><span class="sxs-lookup"><span data-stu-id="23900-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23900-104">语法</span><span class="sxs-lookup"><span data-stu-id="23900-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23900-105">参数</span><span class="sxs-lookup"><span data-stu-id="23900-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="23900-106">弄一个指针，指向[ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md)枚举的值，该值指示当前正在执行的任务的类型。</span><span class="sxs-lookup"><span data-stu-id="23900-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23900-107">要求</span><span class="sxs-lookup"><span data-stu-id="23900-107">Requirements</span></span>  
 <span data-ttu-id="23900-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="23900-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23900-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="23900-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23900-110">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="23900-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23900-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23900-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23900-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="23900-112">See also</span></span>

- [<span data-ttu-id="23900-113">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="23900-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
