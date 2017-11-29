---
title: "ICorDebugExceptionObjectValue::EnumerateExceptionCallStack 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 861d2ad5f9ce0fcc11ea7b1743cd369235cbd878
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="cb310-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack 方法</span><span class="sxs-lookup"><span data-stu-id="cb310-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="cb310-103">到嵌入在异常对象的调用堆栈中获取一个枚举器。</span><span class="sxs-lookup"><span data-stu-id="cb310-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb310-104">语法</span><span class="sxs-lookup"><span data-stu-id="cb310-104">Syntax</span></span>  
  
```  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb310-105">参数</span><span class="sxs-lookup"><span data-stu-id="cb310-105">Parameters</span></span>  
 <span data-ttu-id="cb310-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="cb310-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="cb310-107">[out]指向的地址的指针[ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)接口对象，它是托管的异常对象的堆栈跟踪枚举器。</span><span class="sxs-lookup"><span data-stu-id="cb310-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb310-108">备注</span><span class="sxs-lookup"><span data-stu-id="cb310-108">Remarks</span></span>  
 <span data-ttu-id="cb310-109">如果没有调用堆栈信息可用，该方法返回`S_OK`，和[ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)是长度为 0 的有效枚举器。</span><span class="sxs-lookup"><span data-stu-id="cb310-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="cb310-110">如果方法不能检索的堆栈跟踪信息，返回值是`E_FAIL`并返回枚举。</span><span class="sxs-lookup"><span data-stu-id="cb310-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="cb310-111">[ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)对象负责从堆栈跟踪数据进行解码`_stackTrace`异常对象的字段。</span><span class="sxs-lookup"><span data-stu-id="cb310-111">The [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb310-112">要求</span><span class="sxs-lookup"><span data-stu-id="cb310-112">Requirements</span></span>  
 <span data-ttu-id="cb310-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cb310-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb310-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb310-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb310-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb310-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb310-116">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb310-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb310-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb310-117">See Also</span></span>  
 [<span data-ttu-id="cb310-118">ICorDebugExceptionObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="cb310-118">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 [<span data-ttu-id="cb310-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="cb310-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
