---
title: ICorDebugProcess5::EnumerateHandles 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
ms.openlocfilehash: e0e68dba1f4d9ac5fa618aa842b823dcc046e70e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129678"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="e9df0-102">ICorDebugProcess5::EnumerateHandles 方法</span><span class="sxs-lookup"><span data-stu-id="e9df0-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="e9df0-103">获取进程中的对象句柄的枚举器。</span><span class="sxs-lookup"><span data-stu-id="e9df0-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9df0-104">语法</span><span class="sxs-lookup"><span data-stu-id="e9df0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9df0-105">参数</span><span class="sxs-lookup"><span data-stu-id="e9df0-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="e9df0-106">中[CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)值的按位组合，用于指定要包括在集合中的句柄的类型。</span><span class="sxs-lookup"><span data-stu-id="e9df0-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="e9df0-107">弄一个指针，指向[ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)的地址，该地址是要进行垃圾回收的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="e9df0-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9df0-108">备注</span><span class="sxs-lookup"><span data-stu-id="e9df0-108">Remarks</span></span>  
 <span data-ttu-id="e9df0-109">`EnumerateHandles` 是支持检查句柄表的 helper 函数。</span><span class="sxs-lookup"><span data-stu-id="e9df0-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="e9df0-110">它类似于[ICorDebugProcess5：： EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)方法，不同之处在于，它不是用所有要进行垃圾回收的对象来填充[ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)集合，而只包含具有来自的句柄的对象句柄表。</span><span class="sxs-lookup"><span data-stu-id="e9df0-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="e9df0-111">`types` 参数指定要包含在集合中的句柄类型。</span><span class="sxs-lookup"><span data-stu-id="e9df0-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="e9df0-112">`types` 可以是[CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)枚举的以下三个成员之一：</span><span class="sxs-lookup"><span data-stu-id="e9df0-112">`types` can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
- <span data-ttu-id="e9df0-113">`CorHandleStrongOnly` （仅限强引用的句柄）。</span><span class="sxs-lookup"><span data-stu-id="e9df0-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
- <span data-ttu-id="e9df0-114">`CorHandleWeakOnly` （仅限弱引用的句柄）。</span><span class="sxs-lookup"><span data-stu-id="e9df0-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
- <span data-ttu-id="e9df0-115">`CorHandleAll` （所有句柄）。</span><span class="sxs-lookup"><span data-stu-id="e9df0-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9df0-116">要求</span><span class="sxs-lookup"><span data-stu-id="e9df0-116">Requirements</span></span>  
 <span data-ttu-id="e9df0-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e9df0-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9df0-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9df0-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9df0-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9df0-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9df0-120">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9df0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9df0-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9df0-121">See also</span></span>

- [<span data-ttu-id="e9df0-122">调试结构</span><span class="sxs-lookup"><span data-stu-id="e9df0-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="e9df0-123">调试</span><span class="sxs-lookup"><span data-stu-id="e9df0-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
