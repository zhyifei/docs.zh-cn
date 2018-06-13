---
title: ICorDebugExceptionObjectValue::EnumerateExceptionCallStack 方法
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09f1bc2ae9d56eeb6a6242c32d14bf950684d69d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415608"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="a0d32-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack 方法</span><span class="sxs-lookup"><span data-stu-id="a0d32-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="a0d32-103">到嵌入在异常对象的调用堆栈中获取一个枚举器。</span><span class="sxs-lookup"><span data-stu-id="a0d32-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0d32-104">语法</span><span class="sxs-lookup"><span data-stu-id="a0d32-104">Syntax</span></span>  
  
```  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0d32-105">参数</span><span class="sxs-lookup"><span data-stu-id="a0d32-105">Parameters</span></span>  
 <span data-ttu-id="a0d32-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="a0d32-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="a0d32-107">[out]指向的地址的指针[ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)接口对象，它是托管的异常对象的堆栈跟踪枚举器。</span><span class="sxs-lookup"><span data-stu-id="a0d32-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0d32-108">备注</span><span class="sxs-lookup"><span data-stu-id="a0d32-108">Remarks</span></span>  
 <span data-ttu-id="a0d32-109">如果没有调用堆栈信息可用，该方法返回`S_OK`，和[ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)是长度为 0 的有效枚举器。</span><span class="sxs-lookup"><span data-stu-id="a0d32-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="a0d32-110">如果方法不能检索的堆栈跟踪信息，返回值是`E_FAIL`并返回枚举。</span><span class="sxs-lookup"><span data-stu-id="a0d32-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="a0d32-111">[ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)对象负责从堆栈跟踪数据进行解码`_stackTrace`异常对象的字段。</span><span class="sxs-lookup"><span data-stu-id="a0d32-111">The [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0d32-112">要求</span><span class="sxs-lookup"><span data-stu-id="a0d32-112">Requirements</span></span>  
 <span data-ttu-id="a0d32-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a0d32-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0d32-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0d32-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0d32-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0d32-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0d32-116">**.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0d32-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0d32-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0d32-117">See Also</span></span>  
 [<span data-ttu-id="a0d32-118">ICorDebugExceptionObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="a0d32-118">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 [<span data-ttu-id="a0d32-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="a0d32-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
