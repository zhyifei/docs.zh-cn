---
title: "ICorDebugAppDomain4::GetObjectForCCW 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: abce5563e8cd7eb0c599e835d0217157cf073485
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="1df9e-102">ICorDebugAppDomain4::GetObjectForCCW 方法</span><span class="sxs-lookup"><span data-stu-id="1df9e-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="1df9e-103">从 COM 可调用包装器 (CCW) 指针获取托管对象。</span><span class="sxs-lookup"><span data-stu-id="1df9e-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1df9e-104">语法</span><span class="sxs-lookup"><span data-stu-id="1df9e-104">Syntax</span></span>  
  
```  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1df9e-105">参数</span><span class="sxs-lookup"><span data-stu-id="1df9e-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="1df9e-106">[in] COM 可调用包装器 (CCW) 指针。</span><span class="sxs-lookup"><span data-stu-id="1df9e-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="1df9e-107">[out]指向表示给定 CCW 指针相对应的托管的对象的"ICorDebugValue"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="1df9e-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1df9e-108">备注</span><span class="sxs-lookup"><span data-stu-id="1df9e-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1df9e-109">要求</span><span class="sxs-lookup"><span data-stu-id="1df9e-109">Requirements</span></span>  
 <span data-ttu-id="1df9e-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1df9e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1df9e-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1df9e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1df9e-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1df9e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1df9e-113">**.NET framework 版本：**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1df9e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1df9e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1df9e-114">See Also</span></span>  
 [<span data-ttu-id="1df9e-115">ICorDebugAppDomain4 接口</span><span class="sxs-lookup"><span data-stu-id="1df9e-115">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 [<span data-ttu-id="1df9e-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="1df9e-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
