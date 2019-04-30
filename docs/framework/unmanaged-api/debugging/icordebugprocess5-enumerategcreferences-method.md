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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0845165e3200d7a5e14715cbe116ea5255aa021
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948767"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="02924-102">ICorDebugProcess5::EnumerateGCReferences 方法</span><span class="sxs-lookup"><span data-stu-id="02924-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="02924-103">获取要进行垃圾回收的过程中的所有对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="02924-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02924-104">语法</span><span class="sxs-lookup"><span data-stu-id="02924-104">Syntax</span></span>  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02924-105">参数</span><span class="sxs-lookup"><span data-stu-id="02924-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="02924-106">[in]一个布尔值，该值指示弱引用是否也要枚举。</span><span class="sxs-lookup"><span data-stu-id="02924-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="02924-107">如果`enumerateWeakReferences`是`true`，则`ppEnum`枚举器包括强引用和弱引用。</span><span class="sxs-lookup"><span data-stu-id="02924-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="02924-108">如果`enumerateWeakReferences`是`false`，该枚举数包含仅强引用。</span><span class="sxs-lookup"><span data-stu-id="02924-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="02924-109">[out]指向的地址的指针[ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) ，它是一个枚举器的对象进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="02924-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02924-110">备注</span><span class="sxs-lookup"><span data-stu-id="02924-110">Remarks</span></span>  
 <span data-ttu-id="02924-111">此方法提供了一种方法来确定进程中的任何托管对象根的完整链，并可用于确定对象仍处于活动状态的原因。</span><span class="sxs-lookup"><span data-stu-id="02924-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02924-112">要求</span><span class="sxs-lookup"><span data-stu-id="02924-112">Requirements</span></span>  
 <span data-ttu-id="02924-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="02924-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02924-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02924-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02924-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02924-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02924-116">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02924-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02924-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="02924-117">See also</span></span>

- [<span data-ttu-id="02924-118">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="02924-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="02924-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="02924-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
