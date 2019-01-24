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
ms.openlocfilehash: 7d2a8818ef180b3522a53e29fa84453ea9033a2a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522396"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="476e6-102">ICLRTaskManager::GetCurrentTaskType 方法</span><span class="sxs-lookup"><span data-stu-id="476e6-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="476e6-103">获取当前正在执行的任务的类型。</span><span class="sxs-lookup"><span data-stu-id="476e6-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="476e6-104">语法</span><span class="sxs-lookup"><span data-stu-id="476e6-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="476e6-105">参数</span><span class="sxs-lookup"><span data-stu-id="476e6-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="476e6-106">[out]指向的值的指针[ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md)枚举，指示当前正在执行的任务的类型。</span><span class="sxs-lookup"><span data-stu-id="476e6-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="476e6-107">要求</span><span class="sxs-lookup"><span data-stu-id="476e6-107">Requirements</span></span>  
 <span data-ttu-id="476e6-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="476e6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="476e6-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="476e6-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="476e6-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="476e6-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="476e6-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="476e6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="476e6-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="476e6-112">See also</span></span>
- [<span data-ttu-id="476e6-113">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="476e6-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
