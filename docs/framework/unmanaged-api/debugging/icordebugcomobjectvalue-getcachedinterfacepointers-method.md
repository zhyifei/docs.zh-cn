---
title: "ICorDebugComObjectValue::GetCachedInterfacePointers 方法"
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
- ICorDebugComObjectValue::GetCachedInterfacePointers
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2b47395235ce21c7d40e4413702e6c655493a739
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="4d9ea-102">ICorDebugComObjectValue::GetCachedInterfacePointers 方法</span><span class="sxs-lookup"><span data-stu-id="4d9ea-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="4d9ea-103">获取在当前运行时可调用包装 (RCW) 上缓存的原始接口指针。</span><span class="sxs-lookup"><span data-stu-id="4d9ea-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d9ea-104">语法</span><span class="sxs-lookup"><span data-stu-id="4d9ea-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d9ea-105">参数</span><span class="sxs-lookup"><span data-stu-id="4d9ea-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="4d9ea-106">[in]一个值，指示该方法将仅返回[!INCLUDE[wrt](../../../../includes/wrt-md.md)]接口 (`IInspectable`接口) 或缓存由运行时可调用包装 (RCW) 的所有 COM 接口。</span><span class="sxs-lookup"><span data-stu-id="4d9ea-106">[in] A value that indicates whether the method will return only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="4d9ea-107">[in]其地址已列要检索的对象数。</span><span class="sxs-lookup"><span data-stu-id="4d9ea-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="4d9ea-108">[out]指向数`CORDB_ADDRESS`中实际返回的值`ptrs`。</span><span class="sxs-lookup"><span data-stu-id="4d9ea-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="4d9ea-109">指向数组的起始地址的指针`CORDB_ADDRESS`包含的地址的值缓存界面对象。</span><span class="sxs-lookup"><span data-stu-id="4d9ea-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d9ea-110">备注</span><span class="sxs-lookup"><span data-stu-id="4d9ea-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d9ea-111">惠?</span><span class="sxs-lookup"><span data-stu-id="4d9ea-111">Requirements</span></span>  
 <span data-ttu-id="4d9ea-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4d9ea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d9ea-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d9ea-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d9ea-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d9ea-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d9ea-115">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d9ea-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d9ea-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d9ea-116">See Also</span></span>  
 [<span data-ttu-id="4d9ea-117">ICorDebugComObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="4d9ea-117">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 [<span data-ttu-id="4d9ea-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="4d9ea-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
