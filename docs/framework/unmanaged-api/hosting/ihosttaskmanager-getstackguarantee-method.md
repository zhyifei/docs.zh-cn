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
ms.openlocfilehash: d76242eb8539f2e8dffbf39b7eaf595664bdce8e
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842018"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="a61b2-102">IHostTaskManager::GetStackGuarantee 方法</span><span class="sxs-lookup"><span data-stu-id="a61b2-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="a61b2-103">获取在堆栈操作完成之后但在关闭进程之前保证可用的堆栈空间量。</span><span class="sxs-lookup"><span data-stu-id="a61b2-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a61b2-104">语法</span><span class="sxs-lookup"><span data-stu-id="a61b2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a61b2-105">参数</span><span class="sxs-lookup"><span data-stu-id="a61b2-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="a61b2-106">弄指向可用字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="a61b2-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a61b2-107">要求</span><span class="sxs-lookup"><span data-stu-id="a61b2-107">Requirements</span></span>  
 <span data-ttu-id="a61b2-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a61b2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a61b2-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a61b2-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a61b2-110">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a61b2-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a61b2-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a61b2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a61b2-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a61b2-112">See also</span></span>

- [<span data-ttu-id="a61b2-113">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="a61b2-113">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
