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
ms.openlocfilehash: e6dd951b0f432d455d95bb60f4c42df64d5bee24
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975987"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="283d9-102">ICorDebugExceptionObjectCallStackEnum 接口</span><span class="sxs-lookup"><span data-stu-id="283d9-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="283d9-103">为嵌入在异常对象中的调用堆栈信息提供枚举器。</span><span class="sxs-lookup"><span data-stu-id="283d9-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="283d9-104">此接口是 ICorDebugEnum 接口的子类。</span><span class="sxs-lookup"><span data-stu-id="283d9-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="283d9-105">方法</span><span class="sxs-lookup"><span data-stu-id="283d9-105">Methods</span></span>  
  
|<span data-ttu-id="283d9-106">方法</span><span class="sxs-lookup"><span data-stu-id="283d9-106">Method</span></span>|<span data-ttu-id="283d9-107">说明</span><span class="sxs-lookup"><span data-stu-id="283d9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="283d9-108">ICorDebugExceptionObjectCallStackEnum：： Next</span><span class="sxs-lookup"><span data-stu-id="283d9-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="283d9-109">获取指定数量的[CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md)对象，这些对象包含有关异常对象的调用堆栈的信息。</span><span class="sxs-lookup"><span data-stu-id="283d9-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="283d9-110">备注</span><span class="sxs-lookup"><span data-stu-id="283d9-110">Remarks</span></span>  
 <span data-ttu-id="283d9-111">`ICorDebugExceptionObjectCallStackEnum`接口实现 ICorDebugEnum 接口。</span><span class="sxs-lookup"><span data-stu-id="283d9-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="283d9-112">`ICorDebugExceptionObjectCallStackEnum`实例通过调用[ICorDebugExceptionObjectValue：： EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)方法填充[CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md)对象。</span><span class="sxs-lookup"><span data-stu-id="283d9-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="283d9-113">可以通过调用[ICorDebugExceptionObjectCallStackEnum：： Next](icordebugexceptionobjectcallstackenum-next-method.md)方法枚举集合中的调用堆栈项</span><span class="sxs-lookup"><span data-stu-id="283d9-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="283d9-114">要求</span><span class="sxs-lookup"><span data-stu-id="283d9-114">Requirements</span></span>  
 <span data-ttu-id="283d9-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="283d9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="283d9-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="283d9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="283d9-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="283d9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="283d9-118">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="283d9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="283d9-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="283d9-119">See also</span></span>

- [<span data-ttu-id="283d9-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="283d9-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="283d9-121">调试</span><span class="sxs-lookup"><span data-stu-id="283d9-121">Debugging</span></span>](index.md)
