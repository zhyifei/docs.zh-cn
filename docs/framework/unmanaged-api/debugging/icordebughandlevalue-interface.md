---
title: ICorDebugHandleValue Interface1
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
ms.openlocfilehash: 102fcff6120822c5de0ede45d43a9cd064270085
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715473"
---
# <a name="icordebughandlevalue-interface1"></a><span data-ttu-id="518bc-102">ICorDebugHandleValue Interface1</span><span class="sxs-lookup"><span data-stu-id="518bc-102">ICorDebugHandleValue Interface1</span></span>
<span data-ttu-id="518bc-103">ICorDebugReferenceValue 表示调试器已为其创建垃圾回收的句柄的引用值的子类。</span><span class="sxs-lookup"><span data-stu-id="518bc-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="518bc-104">方法</span><span class="sxs-lookup"><span data-stu-id="518bc-104">Methods</span></span>  
  
|<span data-ttu-id="518bc-105">方法</span><span class="sxs-lookup"><span data-stu-id="518bc-105">Method</span></span>|<span data-ttu-id="518bc-106">描述</span><span class="sxs-lookup"><span data-stu-id="518bc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="518bc-107">Dispose 方法</span><span class="sxs-lookup"><span data-stu-id="518bc-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="518bc-108">释放此引用的句柄`ICorDebugHandleValue`而无需显式地释放接口指针的对象。</span><span class="sxs-lookup"><span data-stu-id="518bc-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="518bc-109">GetHandleType 方法</span><span class="sxs-lookup"><span data-stu-id="518bc-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="518bc-110">获取说明的句柄引用的类型的 CorDebugHandleType 值`ICorDebugHandleValue`。</span><span class="sxs-lookup"><span data-stu-id="518bc-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="518bc-111">备注</span><span class="sxs-lookup"><span data-stu-id="518bc-111">Remarks</span></span>  
 <span data-ttu-id="518bc-112">`ICorDebugReferenceValue`对象失效的调试代码执行过程中中断。</span><span class="sxs-lookup"><span data-stu-id="518bc-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="518bc-113">`ICorDebugHandleValue`显式释放前将保留在中断和继续符，其引用。</span><span class="sxs-lookup"><span data-stu-id="518bc-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="518bc-114">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="518bc-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="518bc-115">要求</span><span class="sxs-lookup"><span data-stu-id="518bc-115">Requirements</span></span>  
 <span data-ttu-id="518bc-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="518bc-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="518bc-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="518bc-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="518bc-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="518bc-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="518bc-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="518bc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="518bc-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="518bc-120">See also</span></span>
- [<span data-ttu-id="518bc-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="518bc-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
