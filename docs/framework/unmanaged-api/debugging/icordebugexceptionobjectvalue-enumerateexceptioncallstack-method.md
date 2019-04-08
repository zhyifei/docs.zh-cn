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
ms.openlocfilehash: db0e794953578fccd08428b730b3d7951e13bee3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074074"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="5f939-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack 方法</span><span class="sxs-lookup"><span data-stu-id="5f939-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="5f939-103">获取嵌入异常对象中的调用堆栈的枚举器。</span><span class="sxs-lookup"><span data-stu-id="5f939-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f939-104">语法</span><span class="sxs-lookup"><span data-stu-id="5f939-104">Syntax</span></span>  
  
```  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f939-105">参数</span><span class="sxs-lookup"><span data-stu-id="5f939-105">Parameters</span></span>  
 <span data-ttu-id="5f939-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="5f939-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="5f939-107">[out]指向的地址的指针[ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)是托管的异常对象的堆栈跟踪枚举器的接口对象。</span><span class="sxs-lookup"><span data-stu-id="5f939-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f939-108">备注</span><span class="sxs-lookup"><span data-stu-id="5f939-108">Remarks</span></span>  
 <span data-ttu-id="5f939-109">如果没有调用堆栈信息不可用，该方法返回`S_OK`，并[ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)是长度为 0 的有效枚举器。</span><span class="sxs-lookup"><span data-stu-id="5f939-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="5f939-110">如果该方法不能检索堆栈跟踪信息，返回值是`E_FAIL`并返回任何枚举器。</span><span class="sxs-lookup"><span data-stu-id="5f939-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="5f939-111">[ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)对象负责的堆栈跟踪数据解码`_stackTrace`异常对象的字段。</span><span class="sxs-lookup"><span data-stu-id="5f939-111">The [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f939-112">要求</span><span class="sxs-lookup"><span data-stu-id="5f939-112">Requirements</span></span>  
 <span data-ttu-id="5f939-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5f939-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f939-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f939-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f939-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f939-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5f939-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="5f939-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5f939-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f939-117">See also</span></span>

- [<span data-ttu-id="5f939-118">ICorDebugExceptionObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="5f939-118">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)
- [<span data-ttu-id="5f939-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="5f939-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
