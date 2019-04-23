---
title: ICorDebug::GetProcess 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dcb869bed71be05e0450580b50dfa9f2a0fca525
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169788"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="33552-102">ICorDebug::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="33552-102">ICorDebug::GetProcess Method</span></span>
<span data-ttu-id="33552-103">获取一个指向到"ICorDebugProcess"实例的指定进程。</span><span class="sxs-lookup"><span data-stu-id="33552-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33552-104">语法</span><span class="sxs-lookup"><span data-stu-id="33552-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33552-105">参数</span><span class="sxs-lookup"><span data-stu-id="33552-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="33552-106">[in]进程的 ID。</span><span class="sxs-lookup"><span data-stu-id="33552-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="33552-107">[out]指向的地址的指针`ICorDebugProcess`指定进程的实例。</span><span class="sxs-lookup"><span data-stu-id="33552-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33552-108">要求</span><span class="sxs-lookup"><span data-stu-id="33552-108">Requirements</span></span>  
 <span data-ttu-id="33552-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="33552-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33552-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33552-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33552-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33552-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33552-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33552-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33552-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="33552-113">See also</span></span>

- [<span data-ttu-id="33552-114">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="33552-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
