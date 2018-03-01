---
title: "ICorDebug::GetProcess 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebug.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::GetProcess method [.NET Framework debugging]
ms.assetid: 10a40ba0-1b65-4721-bd11-cf12d57b280d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3acdcb15f22c130601394ee1bb259207e5e3df23
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="e5d36-102">ICorDebug::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="e5d36-102">ICorDebug::GetProcess Method</span></span>
<span data-ttu-id="e5d36-103">获取一个指向到"ICorDebugProcess"实例的指定的进程。</span><span class="sxs-lookup"><span data-stu-id="e5d36-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5d36-104">语法</span><span class="sxs-lookup"><span data-stu-id="e5d36-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5d36-105">参数</span><span class="sxs-lookup"><span data-stu-id="e5d36-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="e5d36-106">[in]进程的 ID。</span><span class="sxs-lookup"><span data-stu-id="e5d36-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="e5d36-107">[out]指向的地址的指针`ICorDebugProcess`指定进程实例。</span><span class="sxs-lookup"><span data-stu-id="e5d36-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5d36-108">惠?</span><span class="sxs-lookup"><span data-stu-id="e5d36-108">Requirements</span></span>  
 <span data-ttu-id="e5d36-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e5d36-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5d36-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5d36-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5d36-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5d36-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5d36-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5d36-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d36-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5d36-113">See Also</span></span>  
 [<span data-ttu-id="e5d36-114">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="e5d36-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
