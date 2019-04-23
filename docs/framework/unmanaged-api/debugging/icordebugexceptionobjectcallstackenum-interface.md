---
title: ICorDebugExceptionObjectCallStackEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7ed6c04a46a767ed122e54df0695429cf923b8a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126199"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="02377-102">ICorDebugExceptionObjectCallStackEnum 接口</span><span class="sxs-lookup"><span data-stu-id="02377-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="02377-103">为嵌入在异常对象中的调用堆栈信息提供枚举器。</span><span class="sxs-lookup"><span data-stu-id="02377-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="02377-104">此接口是 ICorDebugEnum 接口子类。</span><span class="sxs-lookup"><span data-stu-id="02377-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="02377-105">方法</span><span class="sxs-lookup"><span data-stu-id="02377-105">Methods</span></span>  
  
|<span data-ttu-id="02377-106">方法</span><span class="sxs-lookup"><span data-stu-id="02377-106">Method</span></span>|<span data-ttu-id="02377-107">描述</span><span class="sxs-lookup"><span data-stu-id="02377-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="02377-108">ICorDebugExceptionObjectCallStackEnum::Next</span><span class="sxs-lookup"><span data-stu-id="02377-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="02377-109">获取指定的数目的[CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)包含有关异常对象的调用堆栈信息的对象。</span><span class="sxs-lookup"><span data-stu-id="02377-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02377-110">备注</span><span class="sxs-lookup"><span data-stu-id="02377-110">Remarks</span></span>  
 <span data-ttu-id="02377-111">`ICorDebugExceptionObjectCallStackEnum`接口实现 ICorDebugEnum 接口。</span><span class="sxs-lookup"><span data-stu-id="02377-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="02377-112">`ICorDebugExceptionObjectCallStackEnum`实例中填入[CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)对象通过调用[icordebugexceptionobjectvalue:: Enumerateexceptioncallstack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="02377-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="02377-113">可以通过调用枚举集合中的调用堆栈项[icordebugexceptionobjectcallstackenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)方法</span><span class="sxs-lookup"><span data-stu-id="02377-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02377-114">要求</span><span class="sxs-lookup"><span data-stu-id="02377-114">Requirements</span></span>  
 <span data-ttu-id="02377-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="02377-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02377-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02377-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02377-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02377-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02377-118">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02377-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02377-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="02377-119">See also</span></span>

- [<span data-ttu-id="02377-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="02377-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="02377-121">调试</span><span class="sxs-lookup"><span data-stu-id="02377-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
