---
title: ICorDebugProcess5::EnumerateGCReferences 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
ms.openlocfilehash: 84b5da043f9bd437ee9099135ba865c1ab23bb9d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129660"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="c27d4-102">ICorDebugProcess5::EnumerateGCReferences 方法</span><span class="sxs-lookup"><span data-stu-id="c27d4-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="c27d4-103">获取一个枚举器，该枚举器用于进程中要进行垃圾回收的所有对象。</span><span class="sxs-lookup"><span data-stu-id="c27d4-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c27d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="c27d4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c27d4-105">参数</span><span class="sxs-lookup"><span data-stu-id="c27d4-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="c27d4-106">中指示是否也要枚举弱引用的布尔值。</span><span class="sxs-lookup"><span data-stu-id="c27d4-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="c27d4-107">如果 `true``enumerateWeakReferences`，则 `ppEnum` 枚举器将同时包含强引用和弱引用。</span><span class="sxs-lookup"><span data-stu-id="c27d4-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="c27d4-108">如果 `false``enumerateWeakReferences`，则枚举器仅包括强引用。</span><span class="sxs-lookup"><span data-stu-id="c27d4-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="c27d4-109">弄一个指针，指向[ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)的地址，该地址是要进行垃圾回收的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="c27d4-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c27d4-110">备注</span><span class="sxs-lookup"><span data-stu-id="c27d4-110">Remarks</span></span>  
 <span data-ttu-id="c27d4-111">此方法提供了一种方法，用于确定进程中任何托管对象的完整根链，并可用于确定对象仍处于活动状态的原因。</span><span class="sxs-lookup"><span data-stu-id="c27d4-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c27d4-112">要求</span><span class="sxs-lookup"><span data-stu-id="c27d4-112">Requirements</span></span>  
 <span data-ttu-id="c27d4-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c27d4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c27d4-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c27d4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c27d4-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c27d4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c27d4-116">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c27d4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c27d4-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="c27d4-117">See also</span></span>

- [<span data-ttu-id="c27d4-118">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="c27d4-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="c27d4-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="c27d4-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
