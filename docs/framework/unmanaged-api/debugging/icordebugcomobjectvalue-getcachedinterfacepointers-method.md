---
title: ICorDebugComObjectValue::GetCachedInterfacePointers 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da0e62250dbef9be93ccee7020e23c3f83e85592
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749899"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="65027-102">ICorDebugComObjectValue::GetCachedInterfacePointers 方法</span><span class="sxs-lookup"><span data-stu-id="65027-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="65027-103">获取缓存在当前运行时可调用包装 (RCW) 上的原始接口指针。</span><span class="sxs-lookup"><span data-stu-id="65027-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65027-104">语法</span><span class="sxs-lookup"><span data-stu-id="65027-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65027-105">参数</span><span class="sxs-lookup"><span data-stu-id="65027-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="65027-106">[in]一个值，指示该方法将返回仅[!INCLUDE[wrt](../../../../includes/wrt-md.md)]接口 (`IInspectable`接口) 或所有缓存的运行时可调用包装 (RCW) 的 COM 接口。</span><span class="sxs-lookup"><span data-stu-id="65027-106">[in] A value that indicates whether the method will return only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="65027-107">[in]要从中检索其地址的对象数。</span><span class="sxs-lookup"><span data-stu-id="65027-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="65027-108">[out]指向数`CORDB_ADDRESS`中实际返回的值`ptrs`。</span><span class="sxs-lookup"><span data-stu-id="65027-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="65027-109">指向数组的起始地址的指针`CORDB_ADDRESS`包含的地址的值缓存接口的对象。</span><span class="sxs-lookup"><span data-stu-id="65027-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65027-110">备注</span><span class="sxs-lookup"><span data-stu-id="65027-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65027-111">要求</span><span class="sxs-lookup"><span data-stu-id="65027-111">Requirements</span></span>  
 <span data-ttu-id="65027-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65027-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65027-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65027-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65027-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65027-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65027-115">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65027-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65027-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="65027-116">See also</span></span>

- [<span data-ttu-id="65027-117">ICorDebugComObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="65027-117">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="65027-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="65027-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
