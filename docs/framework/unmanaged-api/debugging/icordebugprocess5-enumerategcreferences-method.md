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
ms.openlocfilehash: a97c14d83f99c847bb8569a33e175ab6eb5bccd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178623"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="3f62d-102">ICorDebugProcess5::EnumerateGCReferences 方法</span><span class="sxs-lookup"><span data-stu-id="3f62d-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="3f62d-103">获取进程中要垃圾回收的所有对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="3f62d-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f62d-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f62d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f62d-105">parameters</span><span class="sxs-lookup"><span data-stu-id="3f62d-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="3f62d-106">[在]指示是否也枚举弱引用的布尔值。</span><span class="sxs-lookup"><span data-stu-id="3f62d-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="3f62d-107">如果是`enumerateWeakReferences``true`，`ppEnum`则枚举器同时包含强引用和弱引用。</span><span class="sxs-lookup"><span data-stu-id="3f62d-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="3f62d-108">如果`enumerateWeakReferences``false`为 ，则枚举器仅包含强引用。</span><span class="sxs-lookup"><span data-stu-id="3f62d-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="3f62d-109">[出]指向[ICorDebugGC 参考Enum](icordebuggcreferenceenum-interface.md)地址的指针，该地址是要垃圾回收的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="3f62d-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f62d-110">备注</span><span class="sxs-lookup"><span data-stu-id="3f62d-110">Remarks</span></span>  
 <span data-ttu-id="3f62d-111">此方法提供了一种确定进程中任何托管对象的完整根链的方法，并可用于确定对象仍然处于活动状态的原因。</span><span class="sxs-lookup"><span data-stu-id="3f62d-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f62d-112">要求</span><span class="sxs-lookup"><span data-stu-id="3f62d-112">Requirements</span></span>  
 <span data-ttu-id="3f62d-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f62d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f62d-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f62d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f62d-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f62d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f62d-116">**.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f62d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f62d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f62d-117">See also</span></span>

- [<span data-ttu-id="3f62d-118">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="3f62d-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="3f62d-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="3f62d-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
