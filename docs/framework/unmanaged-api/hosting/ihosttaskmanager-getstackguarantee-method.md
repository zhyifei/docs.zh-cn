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
ms.openlocfilehash: 089aaf96a164be7eaa258dec65807bd75c998eb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440965"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="52cc0-102">IHostTaskManager::GetStackGuarantee 方法</span><span class="sxs-lookup"><span data-stu-id="52cc0-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="52cc0-103">获取量的保证将之后堆栈操作完成，可用的堆栈空间但在进程结束之前。</span><span class="sxs-lookup"><span data-stu-id="52cc0-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52cc0-104">语法</span><span class="sxs-lookup"><span data-stu-id="52cc0-104">Syntax</span></span>  
  
```  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52cc0-105">参数</span><span class="sxs-lookup"><span data-stu-id="52cc0-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="52cc0-106">[out]指向可用的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="52cc0-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52cc0-107">要求</span><span class="sxs-lookup"><span data-stu-id="52cc0-107">Requirements</span></span>  
 <span data-ttu-id="52cc0-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="52cc0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52cc0-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="52cc0-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="52cc0-110">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="52cc0-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="52cc0-111">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52cc0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52cc0-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="52cc0-112">See Also</span></span>  
 [<span data-ttu-id="52cc0-113">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="52cc0-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
