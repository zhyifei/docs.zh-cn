---
title: "ICorDebugProcess5::EnumerateGCReferences 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.EnumerateGCReferences
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4f517415412c93b009df81fc9a7f524449eb82a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="86a54-102">ICorDebugProcess5::EnumerateGCReferences 方法</span><span class="sxs-lookup"><span data-stu-id="86a54-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="86a54-103">获取要进行垃圾回收的过程中的所有对象的枚举数。</span><span class="sxs-lookup"><span data-stu-id="86a54-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86a54-104">语法</span><span class="sxs-lookup"><span data-stu-id="86a54-104">Syntax</span></span>  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="86a54-105">参数</span><span class="sxs-lookup"><span data-stu-id="86a54-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="86a54-106">[in]一个布尔值，该值指示弱引用是否也要进行枚举。</span><span class="sxs-lookup"><span data-stu-id="86a54-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="86a54-107">如果`enumerateWeakReferences`是`true`、`ppEnum`枚举器包括的强引用和弱引用。</span><span class="sxs-lookup"><span data-stu-id="86a54-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="86a54-108">如果`enumerateWeakReferences`是`false`，该枚举数包含仅的强引用。</span><span class="sxs-lookup"><span data-stu-id="86a54-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="86a54-109">[out]指向的地址的指针[ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)即的枚举数对象要进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="86a54-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86a54-110">备注</span><span class="sxs-lookup"><span data-stu-id="86a54-110">Remarks</span></span>  
 <span data-ttu-id="86a54-111">此方法使您能够确定在进程中任何托管对象的完整根链，并且可以用于确定对象的仍处于活动状态的原因。</span><span class="sxs-lookup"><span data-stu-id="86a54-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86a54-112">要求</span><span class="sxs-lookup"><span data-stu-id="86a54-112">Requirements</span></span>  
 <span data-ttu-id="86a54-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="86a54-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86a54-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86a54-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86a54-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86a54-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86a54-116">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86a54-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86a54-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86a54-117">See Also</span></span>  
 [<span data-ttu-id="86a54-118">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="86a54-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="86a54-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="86a54-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
