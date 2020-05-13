---
title: ICorDebugHandleValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue
helpviewer_keywords:
- ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type:
- apiref
ms.openlocfilehash: c901e21521e941c51939958175a5316808890e9f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208611"
---
# <a name="icordebughandlevalue-interface"></a><span data-ttu-id="3fad9-102">ICorDebugHandleValue 接口</span><span class="sxs-lookup"><span data-stu-id="3fad9-102">ICorDebugHandleValue Interface</span></span>

<span data-ttu-id="3fad9-103">ICorDebugReferenceValue 的子类，表示调试器已为其创建了垃圾回收句柄的引用值。</span><span class="sxs-lookup"><span data-stu-id="3fad9-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3fad9-104">方法</span><span class="sxs-lookup"><span data-stu-id="3fad9-104">Methods</span></span>  
  
|<span data-ttu-id="3fad9-105">方法</span><span class="sxs-lookup"><span data-stu-id="3fad9-105">Method</span></span>|<span data-ttu-id="3fad9-106">描述</span><span class="sxs-lookup"><span data-stu-id="3fad9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3fad9-107">Dispose 方法</span><span class="sxs-lookup"><span data-stu-id="3fad9-107">Dispose Method</span></span>](icordebughandlevalue-dispose-method.md)|<span data-ttu-id="3fad9-108">释放此对象所引用的句柄， `ICorDebugHandleValue` 而不显式释放接口指针。</span><span class="sxs-lookup"><span data-stu-id="3fad9-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="3fad9-109">GetHandleType 方法</span><span class="sxs-lookup"><span data-stu-id="3fad9-109">GetHandleType Method</span></span>](icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="3fad9-110">获取一个 CorDebugHandleType 值，该值描述此所引用的句柄的类型 `ICorDebugHandleValue` 。</span><span class="sxs-lookup"><span data-stu-id="3fad9-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fad9-111">备注</span><span class="sxs-lookup"><span data-stu-id="3fad9-111">Remarks</span></span>  
 <span data-ttu-id="3fad9-112">当 `ICorDebugReferenceValue` 执行调试的代码时，对象会失效。</span><span class="sxs-lookup"><span data-stu-id="3fad9-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="3fad9-113">`ICorDebugHandleValue`通过中断和继续来维护其引用，直到显式释放它。</span><span class="sxs-lookup"><span data-stu-id="3fad9-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3fad9-114">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="3fad9-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fad9-115">要求</span><span class="sxs-lookup"><span data-stu-id="3fad9-115">Requirements</span></span>  
 <span data-ttu-id="3fad9-116">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3fad9-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fad9-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3fad9-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fad9-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fad9-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fad9-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fad9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fad9-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fad9-120">See also</span></span>

- [<span data-ttu-id="3fad9-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="3fad9-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
