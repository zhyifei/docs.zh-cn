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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3219554cf953b8de31e236b2f484478172673f7b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915006"
---
# <a name="icordebughandlevalue-interface"></a><span data-ttu-id="98138-102">ICorDebugHandleValue 接口</span><span class="sxs-lookup"><span data-stu-id="98138-102">ICorDebugHandleValue Interface</span></span>

<span data-ttu-id="98138-103">ICorDebugReferenceValue 的子类, 表示调试器已为其创建了垃圾回收句柄的引用值。</span><span class="sxs-lookup"><span data-stu-id="98138-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98138-104">方法</span><span class="sxs-lookup"><span data-stu-id="98138-104">Methods</span></span>  
  
|<span data-ttu-id="98138-105">方法</span><span class="sxs-lookup"><span data-stu-id="98138-105">Method</span></span>|<span data-ttu-id="98138-106">描述</span><span class="sxs-lookup"><span data-stu-id="98138-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98138-107">Dispose 方法</span><span class="sxs-lookup"><span data-stu-id="98138-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="98138-108">释放此`ICorDebugHandleValue`对象所引用的句柄, 而不显式释放接口指针。</span><span class="sxs-lookup"><span data-stu-id="98138-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="98138-109">GetHandleType 方法</span><span class="sxs-lookup"><span data-stu-id="98138-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="98138-110">获取一个 CorDebugHandleType 值, 该值描述此`ICorDebugHandleValue`所引用的句柄的类型。</span><span class="sxs-lookup"><span data-stu-id="98138-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98138-111">备注</span><span class="sxs-lookup"><span data-stu-id="98138-111">Remarks</span></span>  
 <span data-ttu-id="98138-112">当执行调试的代码时,对象会失效。`ICorDebugReferenceValue`</span><span class="sxs-lookup"><span data-stu-id="98138-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="98138-113">通过中断和继续来维护其引用,直到显式释放它。`ICorDebugHandleValue`</span><span class="sxs-lookup"><span data-stu-id="98138-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98138-114">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="98138-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98138-115">要求</span><span class="sxs-lookup"><span data-stu-id="98138-115">Requirements</span></span>  
 <span data-ttu-id="98138-116">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="98138-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98138-117">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="98138-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98138-118">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98138-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98138-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98138-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98138-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="98138-120">See also</span></span>

- [<span data-ttu-id="98138-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="98138-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
