---
title: ICorDebugAppDomain4::GetObjectForCCW 方法
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9eeb0b80ba691d813e3193f7ae746129c6725e1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506532"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="8eae8-102">ICorDebugAppDomain4::GetObjectForCCW 方法</span><span class="sxs-lookup"><span data-stu-id="8eae8-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="8eae8-103">从 COM 可调用包装器 (CCW) 指针获取托管对象。</span><span class="sxs-lookup"><span data-stu-id="8eae8-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eae8-104">语法</span><span class="sxs-lookup"><span data-stu-id="8eae8-104">Syntax</span></span>  
  
```  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8eae8-105">参数</span><span class="sxs-lookup"><span data-stu-id="8eae8-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="8eae8-106">[in] COM 可调用包装器 (CCW) 指针。</span><span class="sxs-lookup"><span data-stu-id="8eae8-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="8eae8-107">[out]指向表示给定 CCW 指针相对应的托管的对象的"ICorDebugValue"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="8eae8-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8eae8-108">备注</span><span class="sxs-lookup"><span data-stu-id="8eae8-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eae8-109">要求</span><span class="sxs-lookup"><span data-stu-id="8eae8-109">Requirements</span></span>  
 <span data-ttu-id="8eae8-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8eae8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8eae8-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8eae8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8eae8-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8eae8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8eae8-113">**.NET Framework 版本：**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eae8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eae8-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="8eae8-114">See also</span></span>
- [<span data-ttu-id="8eae8-115">ICorDebugAppDomain4 接口</span><span class="sxs-lookup"><span data-stu-id="8eae8-115">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)
- [<span data-ttu-id="8eae8-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="8eae8-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
