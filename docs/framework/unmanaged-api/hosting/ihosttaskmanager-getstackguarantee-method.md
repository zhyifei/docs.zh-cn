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
ms.openlocfilehash: 22ec34c82d0f8e550dfc8941f2c048ebed6cf1d7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133027"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="12b4d-102">IHostTaskManager::GetStackGuarantee 方法</span><span class="sxs-lookup"><span data-stu-id="12b4d-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="12b4d-103">获取在堆栈操作完成之后但在关闭进程之前保证可用的堆栈空间量。</span><span class="sxs-lookup"><span data-stu-id="12b4d-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12b4d-104">语法</span><span class="sxs-lookup"><span data-stu-id="12b4d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12b4d-105">参数</span><span class="sxs-lookup"><span data-stu-id="12b4d-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="12b4d-106">弄指向可用字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="12b4d-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12b4d-107">要求</span><span class="sxs-lookup"><span data-stu-id="12b4d-107">Requirements</span></span>  
 <span data-ttu-id="12b4d-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="12b4d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12b4d-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="12b4d-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="12b4d-110">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="12b4d-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12b4d-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12b4d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12b4d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="12b4d-112">See also</span></span>

- [<span data-ttu-id="12b4d-113">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="12b4d-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
