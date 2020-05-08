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
ms.openlocfilehash: e45b180ac6d943d89740ad7ae10500ea4ad1aa9c
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975961"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="5b974-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack 方法</span><span class="sxs-lookup"><span data-stu-id="5b974-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="5b974-103">获取一个枚举器，该枚举器指向嵌入到异常对象中的调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="5b974-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b974-104">语法</span><span class="sxs-lookup"><span data-stu-id="5b974-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b974-105">参数</span><span class="sxs-lookup"><span data-stu-id="5b974-105">Parameters</span></span>  
 <span data-ttu-id="5b974-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="5b974-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="5b974-107">弄指向[ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)接口对象地址的指针，该对象是托管异常对象的堆栈跟踪枚举器。</span><span class="sxs-lookup"><span data-stu-id="5b974-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b974-108">备注</span><span class="sxs-lookup"><span data-stu-id="5b974-108">Remarks</span></span>  
 <span data-ttu-id="5b974-109">如果没有可用的调用堆栈信息，则该方法`S_OK`将返回，并且[ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)是长度为0的有效枚举器。</span><span class="sxs-lookup"><span data-stu-id="5b974-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="5b974-110">如果该方法无法检索堆栈跟踪信息，则返回值为`E_FAIL` ，并且不返回任何枚举器。</span><span class="sxs-lookup"><span data-stu-id="5b974-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="5b974-111">[ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)对象负责从 exception 对象的`_stackTrace`字段解码堆栈跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="5b974-111">The [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b974-112">要求</span><span class="sxs-lookup"><span data-stu-id="5b974-112">Requirements</span></span>  
 <span data-ttu-id="5b974-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5b974-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b974-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b974-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b974-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b974-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b974-116">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b974-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b974-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b974-117">See also</span></span>

- [<span data-ttu-id="5b974-118">ICorDebugExceptionObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="5b974-118">ICorDebugExceptionObjectValue Interface</span></span>](icordebugexceptionobjectvalue-interface.md)
- [<span data-ttu-id="5b974-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="5b974-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
