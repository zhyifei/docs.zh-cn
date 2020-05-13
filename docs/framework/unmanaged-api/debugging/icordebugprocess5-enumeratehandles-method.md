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
ms.openlocfilehash: 291b384d6f0c8c1404b380c653693ec65fcfc960
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213408"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="86ce9-102">ICorDebugProcess5::EnumerateHandles 方法</span><span class="sxs-lookup"><span data-stu-id="86ce9-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="86ce9-103">获取进程中的对象句柄的枚举器。</span><span class="sxs-lookup"><span data-stu-id="86ce9-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86ce9-104">语法</span><span class="sxs-lookup"><span data-stu-id="86ce9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86ce9-105">参数</span><span class="sxs-lookup"><span data-stu-id="86ce9-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="86ce9-106">中[CorGCReferenceType](corgcreferencetype-enumeration.md)值的按位组合，用于指定要包括在集合中的句柄的类型。</span><span class="sxs-lookup"><span data-stu-id="86ce9-106">[in] A bitwise combination of [CorGCReferenceType](corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="86ce9-107">弄一个指针，指向[ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)的地址，该地址是要进行垃圾回收的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="86ce9-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86ce9-108">备注</span><span class="sxs-lookup"><span data-stu-id="86ce9-108">Remarks</span></span>  
 <span data-ttu-id="86ce9-109">`EnumerateHandles`是支持对句柄表的检查的 helper 函数。</span><span class="sxs-lookup"><span data-stu-id="86ce9-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="86ce9-110">它类似于[ICorDebugProcess5：： EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md)方法，不同之处在于，它不是用所有要进行垃圾回收的对象填充[ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)集合，只包括具有句柄表中的句柄的对象。</span><span class="sxs-lookup"><span data-stu-id="86ce9-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="86ce9-111">`types`参数指定要包括在集合中的句柄类型。</span><span class="sxs-lookup"><span data-stu-id="86ce9-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="86ce9-112">`types`可以是[CorGCReferenceType](corgcreferencetype-enumeration.md)枚举的以下三个成员之一：</span><span class="sxs-lookup"><span data-stu-id="86ce9-112">`types` can be any of the following three members of the [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
- <span data-ttu-id="86ce9-113">`CorHandleStrongOnly`（仅限强引用的句柄）。</span><span class="sxs-lookup"><span data-stu-id="86ce9-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
- <span data-ttu-id="86ce9-114">`CorHandleWeakOnly`（仅限弱引用的句柄）。</span><span class="sxs-lookup"><span data-stu-id="86ce9-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
- <span data-ttu-id="86ce9-115">`CorHandleAll`（所有句柄）。</span><span class="sxs-lookup"><span data-stu-id="86ce9-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86ce9-116">要求</span><span class="sxs-lookup"><span data-stu-id="86ce9-116">Requirements</span></span>  
 <span data-ttu-id="86ce9-117">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="86ce9-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86ce9-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86ce9-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86ce9-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86ce9-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86ce9-120">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86ce9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86ce9-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="86ce9-121">See also</span></span>

- [<span data-ttu-id="86ce9-122">调试结构</span><span class="sxs-lookup"><span data-stu-id="86ce9-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="86ce9-123">调试</span><span class="sxs-lookup"><span data-stu-id="86ce9-123">Debugging</span></span>](index.md)
